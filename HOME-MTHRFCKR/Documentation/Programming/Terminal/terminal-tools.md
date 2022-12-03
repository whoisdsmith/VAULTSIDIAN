##### Tool: [terminal](https://en.wikipedia.org/wiki/Linux_console)

###### Reload shell without exit

###### Close shell keeping all subprocess running

###### Exit without saving shell history

kill -9 $$  
unset HISTFILE && exit

###### Perform a branching conditional

true && echo success  
false || echo failed

###### Pipe stdout and stderr to separate commands

some_command > >(/bin/cmd_for_stdout) 2> >(/bin/cmd_for_stderr)

###### Redirect stdout and stderr each to separate files and print both to the screen

(some_command 2>&1 1>&3 | tee errorlog ) 3>&1 1>&2 | tee stdoutlog

###### List of commands you use most often

history | \  
awk '{CMD[$2]++;count++;}END { for (a in CMD)print CMD[a] " " CMD[a]/count*100 "% " a;}' | \  
grep -v "./" | \  
column -c3 -s " " -t | \  
sort -nr | nl | head -n 20

###### Sterilize bash history

function sterile() {

history | awk '$2 != "history" { $1=""; print $0 }' | egrep -vi "\  
curl\b+.*(-E|--cert)\b+.*\b*|\  
curl\b+.*--pass\b+.*\b*|\  
curl\b+.*(-U|--proxy-user).*:.*\b*|\  
curl\b+.*(-u|--user).*:.*\b*  
.*(-H|--header).*(token|auth.*)\b+.*|\  
wget\b+.*--.*password\b+.*\b*|\  
http.?://.+:.+@.*\  
" > $HOME/histbuff; history -r $HOME/histbuff;

}

export PROMPT_COMMAND="sterile"