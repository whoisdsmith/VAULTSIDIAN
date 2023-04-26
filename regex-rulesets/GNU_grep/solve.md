dir_name=$(basename "$PWD")
ref_file="../.ref_solutions/$dir_name.txt"
sol_file="../$dir_name.txt"
tmp_file='../.tmp.txt'

# color output
tcolors=$(tput colors)
if [[ -n $tcolors && $tcolors -ge 8 ]]; then
    red=$(tput setaf 1)
    green=$(tput setaf 2)
    blue=$(tput setaf 4)
    clr_color=$(tput sgr0)
else
    red=''
    green=''
    blue=''
    clr_color=''
fi

sub_sol=0
if [[ $1 == -s ]]; then
    prev_cmd=$(fc -ln -2 | sed 's/^[ \t]*//;q')
    sub_sol=1
elif [[ $1 == -q ]]; then
    # highlight the question to be solved next
    # or show only the (unanswered)? question to be solved next
    cat "$sol_file"
    return
elif [[ -n $1 ]]; then
    echo -e 'Unknown option...Exiting script'
    return
fi

count=0
sol_count=0
err_count=0
while IFS= read -u3 -r ref_line && read -u4 -r sol_line; do
    if [[ "${ref_line:0:9}" == Solution: ]]; then
        (( count++ ))

        if [[ $sub_sol == 1 && -z $sol_line ]]; then
            sol_line="$prev_cmd"
            sub_sol=0
        fi

        if [[ "$(eval "command ${ref_line:10}")" == "$(eval "command $sol_line")" ]]; then
            (( sol_count++ ))
            # use color if terminal supports
            echo '---------------------------------------------'
            echo "Match for question $count:"
            echo "${red}Submitted solution:${clr_color} $sol_line"
            echo "${green}Reference solution:${clr_color} ${ref_line:10}"
            echo '---------------------------------------------'
        else
            (( err_count++ ))
            if [[ $err_count == 1 && -n $sol_line ]]; then
                echo '---------------------------------------------'
                echo "Mismatch for question $count:"
                echo "$(tput bold)${red}Expected output is:${clr_color}$(tput rmso)"
                eval "command ${ref_line:10}"
                echo '---------------------------------------------'
            fi
            sol_line=''
        fi
    fi

    echo "$sol_line" >> "$tmp_file"

done 3<"$ref_file" 4<"$sol_file"

((count==sol_count)) && printf "\t\t$(tput bold)${blue}All Pass${clr_color}$(tput rmso)\t\t\n"

mv "$tmp_file" "$sol_file"

# vim: syntax=bash
