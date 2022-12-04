# Software-Tools

## Software-Tools

***

## Color Picker

* [Sip](https://sipapp.io/)

## API Tool

* [Paw](https://paw.cloud/)
* [Postman](https://www.getpostman.com/)
* [Insomnia](https://insomnia.rest/)

## Markdown Editor

* [MacDown](https://github.com/MacDownApp/macdown)

## a11y

* `tabIndex="0"`
* `aria-label="add"`
* `aria-hidden="true"`

## ASDF

Manage multiple runtime versions with a single CLI tool, extendable via plugins - docs at asdf-vm.com

asdf-vm is a CLI tool that can manage multiple language runtime versions on a per-project basis. It is like gvm, nvm, rbenv & pyenv (and more) all in one! Simply install your language's plugin!

https://asdf-vm.com/#/core-manage-asdf-vm

### Installation

https://asdf-vm.com/#/core-manage-asdf?id=install

mac

```
brew install asdf
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
```

linux

```
sudo apt install curl git
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.0
```

Add the following to \~/.bashrc:

```
. $HOME/.asdf/asdf.sh
```

Completions must be configured by adding the following to your .bashrc:

```
. $HOME/.asdf/completions/asdf.bash
```

```
asdf plugin list
```

### Python

https://github.com/danhper/asdf-python

```
brew uninstall python python3 pyenv python@3.8
asdf plugin-add python
asdf list python
asdf install python latest
asdf global python 3.6.2
```

### Ruby

```
asdf plugin-add ruby https://github.com/asdf-vm/asdf-ruby.git
asdf install ruby latest
asdf global ruby 2.7.1
```

### Nodejs

https://github.com/asdf-vm/asdf-nodejs

```
GNU Core Utils - brew install coreutils
GnuPG - brew install gpg
brew install gawk
bash -c '${ASDF_DATA_DIR:=$HOME/.asdf}/plugins/nodejs/bin/import-release-team-keyring'
asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
asdf list nodejs
asdf install nodejs latest
asdf install nodejs 12.12.0
asdf global nodejs 12.12.0
```

## SSO

* LDAP
* SAML

## Node

* [passportjs](http://www.passportjs.org/)

## JWT

benefit vs session?

## Session

* session cookie?

## Ref

[Session vs Token Based Authentication](https://medium.com/@sherryhsu/session-vs-token-based-authentication-11a6c5ac45e4)

## Chrome-bookmark

`javascript:window.prompt("Copy to clipboard: Ctrl+C, Enter",`[${document.title}](../Software%20Tools/$%7Bdocument.URL%7D)`);`

## Circleci

### 2.0 With GEK

https://discuss.circleci.com/t/google-container-registry-push-image/12301/22

Build Docker image\  
Install Google SDK\  
tag image using command docker tag…

gcloud auth to service account using json file (as security move this file to private repository or private server)\  
gcloud docker --push and other you arguments.

## Cms

### CMS

* \[Wordpress]
* [GHost](https://ghost.org/)
  * https://stratechery.com/2019/ghost-3-0-an-interview-with-ghost-ceo-john-onolan/
  * Yet another CMS solution https://ghost.org/, not a headless one. If I’m going to do another CMS stuff again I think I’ll give it a try

### Headless CMS

* [strapi](https://strapi.io/) Open source, Node based.
* [Forestry.io](https://forestry.io/) 不是 API 的形式，是直接 commit 進你的 repository
* [Contentful](https://www.contentful.com/) 覺得滿漂亮好用的，但超貴
* [Netlify CMS](https://www.netlifycms.org/)
* [GraphCMS](https://graphcms.com/) 有點醜…雖然是用 Material Design 整套下去做的，功能上和 Contentful 感覺沒差多少，除了有個 API Explorer
* [Prismic](https://prismic.io/)

[Picking a back-end for GatsbyJS | GatsbyJS](https://www.gatsbyjs.org/blog/2018-2-6-choosing-a-back-end/)\  
Best of the rest - Prismic.io & Cockpit\  
Prismic is sort of a Contentful-like service that does basically the same thing with a few differences. I’m greeted to a post-type-creator similar to Contentful’s, I can create an editor with a number of fields similar such as Title, Body, Image, Location, Link, Color.

* [Gentics Mesh](https://github.com/gentics/mesh) The open source headless CMS for developers

###


## Co-working-space

* [Treeful . 小樹屋](https://www.treerful.com/)
* [趣工作](https://www.keepworking.com.tw/)

[cron cheatsheet](https://devhints.io/cron)\  
[The Ultimate Crontab Cheatsheet](https://www.codementor.io/akul08/the-ultimate-crontab-cheatsheet-5op0f7o4r)

## Format

Min Hour Day Mon Weekday

```
* * * * * command to be executed
┬ ┬ ┬ ┬ ┬
│ │ │ │ └─ Weekday (0=Sun .. 6=Sat)
│ │ │ └────── Month (1..12)
│ │ └─────────── Day (1..31)
│ └──────────────── Hour (0..23)
└───────────────────── Minute (0..59)
```

## Crontab

```
# Adding tasks easily
echo "@reboot echo hi" | crontab
# Open in editor
crontab -e
# List tasks
crontab -l [-u user]
```

* \-e (edit user's crontab)
* \-l (list user's crontab)
* \-r (delete user's crontab)
* \-i (prompt before deleting user's crontab)

```
crontab -e
* * * * * cd ~/app/pangolin && /usr/local/bin/docker-compose run -d --no-deps crawler node src/getStation.js
```

```
crontab -l
```

## Log

```
sudo grep CRON /var/log/syslog*
sudo grep CRON /var/log/syslog* | grep -E "(yes)"
```

## Crypto Links

### Crypto Exchanges:

* Binance: https://www.binance.com ⭐
* Crypto.com https://crypto.com ⭐
* KuCoin https://www.kucoin.com
* FTX https://ftx.com

### Basics Analytics Tools

* CoinGecko https://www.coingecko.com ⭐
* CoinMarketCap https://coinmarketcap.com ⭐
* TradingView https://www.tradingview.com ⭐
* Coin360 https://coin360.com

### Onchain Data Analytics Tools

* Glassnode https://glassnode.com ⭐

### YouTube Channels

* Piotr Ostapowicz https://www.youtube.com/c/PiotrOstapowicz1 ⭐
* Phil Konieczny https://www.youtube.com/c/PhilKonieczny ⭐
* The Birb Nest https://www.youtube.com/c/TheBirbNest ⭐
* Dzienna Dawka Dyskomfortu https://www.youtube.com/c/DziennaDawkaDyskomfortu

### Twitter

* @crypto\_birb https://twitter.com/crypto\_birb ⭐
* @piotr\_rataj https://twitter.com/piotr\_rataj ⭐
* @PanParagraf https://twitter.com/PanParagraf
* @kamilgancarz https://twitter.com/kamilgancarz
* @PiotrOstapowicz https://twitter.com/PiotrOstapowicz
* @jarzoombek https://twitter.com/jarzoombek
* @BTC\_Archive https://twitter.com/BTC\_Archive
* @AltcoinDailyio https://twitter.com/AltcoinDailyio

### Wallets

#### Web/App

* MetaMask https://metamask.io ⭐
* Terra Station https://station.terra.money ⭐
* Exodus https://www.exodus.com ⭐
* Phantom https://phantom.app
* Solflare https://solflare.com

#### Physical

* Ledger https://shop.ledger.com ⭐
* Trezor https://trezor.io
* [Everything curl](https://ec.haxx.se/)

## Get Request Time

```
-w %{time_connect}:%{time_starttransfer}:%{time_total}
```

## Get

```
curl http://localhost:3000/users
```

## Post

```
curl \
  -i \
  -X POST \
  -H "Content-Type: application/json" \
  -d '{"username":"yes","password":"yes"}' \
  http://localhost:3000/signup
```

* [`--data, -d`](../Software%20Tools/\(https:/curl.haxx.se/docs/manpage.html#-d\)): Sends the specified data in a POST request to the HTTP server.
* \--include, -i: All HTTP replies contain a set of response headers that are normally hidden, use curl's --include (-i) option to display them as well as the rest of the document.
* \--request, -X : Change the method keyword curl selects.

### Get Cookie From Response

TBD

response.headers\["set-cookie"]

## Wait Until Localhost Post Open

https://stackoverflow.com/questions/11904772/how-to-create-a-loop-in-bash-that-is-waiting-for-a-webserver-to-respond

```
until $(curl --output /dev/null --silent --head --fail http://myhost:myport); do
    printf '.'
    sleep 5
done
```

```
- [--output](https://curl.haxx.se/docs/manpage.html#-o): Write output to <file> instead of stdout.
- [--silent](https://curl.haxx.se/docs/manpage.html#-s): Silent or quiet mode. Don't show progress meter or error messages.
- [--head](https://curl.haxx.se/docs/manpage.html#-I): (HTTP FTP FILE) Fetch the headers only!
- [--fail](https://curl.haxx.se/docs/manpage.html#-f): (HTTP) Fail silently (no output at all) on server errors.
```

## Standard

* [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html)
  * [wiki](https://www.iso.org/iso-3166-country-codes.html)

CODE SHOULD BE UPPERCASE!

## Attributes

## Country List

## Editor

* [Oni - Modern Modal Editing](https://www.onivim.io/)

## HTTP Request

## HTTP Response

charset = big5 怎處理?

氣象局 https://e-service.cwb.gov.tw/wdps/obs/state.htm

solution https://dotblogs.com.tw/wasichris/2015/08/29/153254

axios solution: https://github.com/axios/axios/issues/332

## UTF-8

Big5

ASCII

Unicode

## Timelapse Video

My post…https://medium.com/@hiiamyes/using-ffmpeg-to-make-time-lapse-video-391f5ea8cc6b

[scale](https://stackoverflow.com/questions/44634765/ffmpeg-aspect-ratio-of-image-in-a-slideshow)

```
ffmpeg -f image2 -pattern_type glob -framerate 30 -i 'G0*.JPG' -vf "scale=3840x2160:force_original_aspect_ratio=decrease,pad=3840:2160:(ow-iw)/2:(oh-ih)/2,setsar=1" -vcodec libx264 -pix_fmt yuv420p test6.mp4
```

```
ffmpeg -f image2 -pattern_type glob -framerate 30 -i 'G0*.JPG' -s 3840x2160 -vcodec libx264 -pix_fmt yuv420p test4.mp4
```

[Why won't video from ffmpeg show in QuickTime, iMovie or quick preview?](https://apple.stackexchange.com/questions/166553/why-wont-video-from-ffmpeg-show-in-quicktime-imovie-or-quick-preview)

In short, you (often) need to include the argument `-pix_fmt yuv420p` when using ffmpeg to generate H.264 content for Apple software/devices, and a bunch of other decoders that don't handle yuv444p.

```
ffmpeg -i input.avi -pix_fmt yuv420p output.mp4
```

This is not mentioned in the output when using the defaults, but can be found in their Encode/H.264 guide.

[Convert sequence of JPEG images to MP4 video](https://gist.github.com/alexellis/bbf2bc2a6789480fcd0031f99800df9c)

`ffmpeg -r 24 -pattern_type glob -i '*.JPG' -i DSC_%04d.JPG -s hd1080 -vcodec libx264 timelapse.mp4`

* `-r 24` - output frame rate
* `-pattern_type glob -i '*.JPG'` - all JPG files in the current directory
* `-i DSC_%04d.JPG` - e.g. DSC\_0397.JPG
* `-s hd1080` - 1920x1080 resolution

\[Padding]\  
[FFMPEG scale video to 720px, add black fields at the top and bottom and output 720x1280 (portrait) \[duplicate\]](https://superuser.com/questions/1271758/ffmpeg-scale-video-to-720px-add-black-fields-at-the-top-and-bottom-and-output-7)

The method below assumes that the source aspect ratio isn't greater than 720/1280.

```
ffmpeg -i in.mp4 -vf scale=720:1280:force_original_aspect_ratio=decrease,pad=720:1280:(ow-iw)/2:(oh-ih)/2,setsar=1 out.mp4
```

The force\_original\_aspect\_ratio in the scale 'fits' the video within the dimensions specified. The pad then expands the canvas to get the size desired.

## GDPR

General Data Protection Regulation

https://gdpr-info.eu/\  
https://gdpr.eu/

https://www.cookiebot.com/en/gdpr-cookies/#:\~:text=GDPR%20cookie%20consent%20is%20when,data%2C%20while%20visiting%20your%20site.

### GDPR Cookie Consent

What is GDPR cookie consent?\  
GDPR cookie consent is when users give their informed, explicit, unambiguous consent to which cookies on your website they will allow to be activated and collect their personal data, while visiting your site. A compliant GDPR cookie consent must be granular, i.e. users must be able to choose some cookies rather than others and not be forced to simply accept or reject all.

### Do All Cookies Require Opt-In?

https://law.stackexchange.com/questions/29083/gdpr-compliance-do-all-cookies-require-opt-in

Not all cookies require consent.

The current answers are in WP 29 Opinion 04/2012 on Cookie Consent Exemption - 00879/12/EN WP 194.

This WP29 Opinion is based upon Directive 2002/58/EC ("ePrivacy Directive"), and not GDPR, which is current law for this matter until other guidelines are adopted pursuant to GDPR or until the awaited "ePrivacy Regulation" is finally adopted.

### Strictly Necessary Cookies

https://stackoverflow.com/questions/50513448/gdpr-and-cookies-that-do-not-store-personal-data?rq=1

However, you don't need consent where the cookie or other technology is "strictly necessary" to provide you with the service the user is seeking–for example, cookies which may be needed to provide you with a functioning website which the user wants to access.

https://gdpr.eu/cookies/#:\~:text=Strictly%20necessary%20cookies%20%E2%80%94%20These%20cookies,example%20of%20strictly%20necessary%20cookies.

Strictly necessary cookies—These cookies are essential for you to browse the website and use its features, such as accessing secure areas of the site. Cookies that allow web shops to hold your items in your cart while you are shopping online are an example of strictly necessary cookies. These cookies will generally be first-party session cookies. While it is not required to obtain consent for these cookies, what they do and why they are necessary should be explained to the user.

[Cookies, the GDPR, and the ePrivacy Directive - GDPR.eu](https://gdpr.eu/cookies/)

### Cookie Compliance

https://gdpr.eu/cookies/#:\~:text=Strictly%20necessary%20cookies%20%E2%80%94%20These%20cookies,example%20of%20strictly%20necessary%20cookies.

To comply with the regulations governing cookies under the GDPR and the ePrivacy Directive you must:

* Receive users’ consent before you use any cookies **except** strictly necessary cookies.
* Provide accurate and specific information about the data each cookie tracks and its purpose in plain language before consent is received.
* Document and store consent received from users.
* Allow users to access your service even if they refuse to allow the use of certain cookies
* Make it as easy for users to withdraw their consent as it was for them to give their consent in the first place.

## Google Sheet

### Fixed Column

\=IFS(ROW() = 4, $W$21 - sum($AG$4:AG7), AK6>0, $W$21 - sum($AG$4:AG7), sum($AG$4:AG7) > $W$21, -AG7)

### Query

\=QUERY(employees!A:D,"select A where C = '"\&B2&"'")

arrayformula for query is not supported

### Vlookup

\=ARRAYFORMULA(VLOOKUP(B3:B,{employees!C2:C, employees!D2:D},2,false))

### Lookup

https://support.google.com/docs/answer/3256570?hl=en

```
```

### Index

https://support.google.com/docs/answer/3098242?hl=en\&ref\_topic=3105472

```
=INDEX(A1:E7, MATCH("Course 3", A:A, 0), MATCH("Pablo", 1:1, 0))
```

## Axios

```
    async function get() {
      const res = await axios.request({
        method: "POST",
        url: "http://localhost:4000",
        data: {
          query: `
          query{
            station(id: "467550") {
              id
              rainfalls {
                date
                value
              }
            }
          }`
        }
      });
      console.log(res);
    }
```

## Grid-system

[IBM/css-gridish](https://github.com/ibm/css-gridish) - Automatically build your grid design’s CSS Grid code, CSS Flexbox fallback code, Sketch artboards, and Chrome extension.

[Grid Garden](https://cssgridgarden.com/)

## Homebrew

`brew install docker`

`brew search docker`

`brew list docker`

## Jira

next release filter

```
assignee = yes AND project = CORE AND fixVersion in ("2019-08-20", EMPTY) OR
```

```
assignee = yes AND project = "EMQ Connect Management" AND (status not in (NEW, CLOSED) OR status = CLOSED AND updatedDate > 2019-08-20) OR 
assignee = yes AND project = "Mobile Team" AND (fixVersion = 2019-08-20 OR fixVersion = EMPTY AND status not in (New, DONE)) OR
assignee = yes AND project = "Web Development" AND (status not in ("To Do", DONE) OR status = DONE AND updatedDate > 2019-08-20)
```

## Linux

### Check Disk Space

https://opensource.com/article/18/7/how-check-free-disk-space-linux

```
<!-- disk free -->
<!-- shows disk space in human-readable format -->
df -h
<!-- shows the file system's complete disk usage even if the Available field is 0 -->
df -a
<!-- shows the disk usage along with each block's filesystem type (e.g., xfs, ext2, ext3, btrfs, etc.) -->
df -T
<!-- shows used and free inodes -->
df -i

<!-- shows the disk usage of files, folders, etc. in the default kilobyte size -->
du
<!-- shows disk usage in human-readable format for all directories and subdirectories -->
du -h
```

### Folder

`/opt/`:

`/srv/`:

`~/`: `/User/current-user/`

## Fix MAC Camera

Fixing “There is no connected camera” Error with a Mac FaceTime Camera

```
sudo killall VDCAssistant
sudo killall AppleCameraAssistant
<!-- No matching processes were found -->
```

## Naming

### Create Vs Add

https://ux.stackexchange.com/questions/43174/update-vs-modify-vs-change-create-vs-add-delete-vs-remove

What's best calling these things depends on:

Who is using the system;\  
what is the nature of the action really being performed;\  
what other actions may be performed.\  
The Programmers View\  
With relation to databases (and data-driven APIs) there's the famous CRUD operations, which stand for Create/Read/Update/Destroy.

In many programming languages you may first create a record, then add it to a container, then remove it from the container, then destroy or delete it.

Also, in programming, change denotes something that is yet to be persisted (saved to the database or file), while update denotes persisting the change. Modify is not common, but you do get 'modified records' as a flag for a non-persisted state (aka, 'dirty records').

Everyday Language\  
You can argue that people will agree on these definitions:

You create something from scratch. Like create a new report.\  
Once in existence, you add something to a container. Like adding a person to the managers group.

By modifying something you change its properties. Like modifying a design.

By updating something you change the data, but not the design. Like updating someone's phone number.\  
By changing something you replace one existing thing with another. Like changing your profile photo.

By removing something you take it out of a container. Like removing something from the fridge - the thing still exist.

By destroying something you do the opposite from creating - gone forever. Like destroying a toy.\  
By deleting something you wipe if off, so it is no longer retrievable. This is said with the obvious exception that nowadays people are accustomed to the 'undelete' feature. So somewhat of an ambiguity here, but it is a standard in interfaces to use the term for permanent delation.\  
My Recommendations\  
Prefer Add over Create unless there's a clear create-then-add mechanism. Although technically (and as you said) create means it never existed before, while programmers think about 'records' users think about the abstraction these stand for. While for you adding a person's record makes perfect sense, 'creating a person' or 'creating a task' is less intuitive than 'adding a person' (to the system) or 'adding a task' (to the task list). Obviously, if your users are IT professionals and fluent with what a database and records are, prefer create over add.\  
If persistance is involved, prefer update over change. Having said that, users are accustomed to 'save changes'. Don't use modify.\  
Prefer Remove for non-permanent removal, and Delete for permanent removal.

## Openssl

```
brew install openssl
```

\==> openssl@1.1\  
A CA file has been bootstrapped using certificates from the system\  
keychain. To add additional certificates, place .pem files in\  
/usr/local/etc/openssl@1.1/certs

and run\  
/usr/local/opt/openssl@1.1/bin/c\_rehash

openssl@1.1 is keg-only, which means it was not symlinked into /usr/local,\  
because macOS provides LibreSSL.

If you need to have openssl@1.1 first in your PATH run:\  
echo 'export PATH="/usr/local/opt/openssl@1.1/bin:$PATH"' >> /Users/yes/.bash\_profile

For compilers to find openssl@1.1 you may need to set:\  
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"\  
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"

For pkg-config to find openssl@1.1 you may need to set:\  
export PKG\_CONFIG\_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig"

## PDF Generator

### Solution

* express
* puppeteer

### PDF Size

```css
body {
  width: 210mm;
  height: 297mm;
  margin-left: auto;
  margin-right: auto;
}
```

## Python

https://docs.python.org/3/tutorial/venv.html#creating-virtual-environments

```
asdf install python 3.9.0
asdf global python 3.9.0
python -m venv myenv
<!-- python -m virtualenv myenv -->
source myenv/bin/activate
pip install -r requirements.txt
```

### Formatter

Proposed Solution

* Formatter: yapf
* VSCode Extension: ms-python\  
  \-- Config: `.vscode/settings.json` and `.style.yapf`\  
  \-- Keyboard Shortcuts: `shift + alt + f`

```
// .vscode/settings.json
{
  "python.pythonPath": "env/bin/python2.7"
}
```

```
// .style.yapf
[style]
based_on_style = google
ALLOW_SPLIT_BEFORE_DICT_VALUE = False
INDENT_DICTIONARY_VALUE = True
SPLIT_BEFORE_FIRST_ARGUMENT = True
```

### Virtualenv

https://virtualenv.pypa.io/en/latest/cli\_interface.html

```
virtualenv env
virtualenv -p /Users/yes/.asdf/shims/python env
source env/bin/active
python --version
pip install -r requirements.txt
```

## [redis-cli](https://redis.io/topics/rediscli)

```
brew install redis
```

### Connect

```
redis-cli -h localhost -p 6379 ping
```

### Create

`set station-123:2019-02-01 "2.3"`

### Read

* [KEYS](https://redis.io/commands/keys)

`KEYS *`

`get station-123:2019-02-01 // 2.3`

### Update

### Delete

## Regexp

[RegExr](https://regexr.com/)

### Number

* 0.0: `/^([0-9]*[.])?[0-9]+/`

## Image

* ImgIX
* [Cloudinary](https://cloudinary.com/)

## Error Tracking

Sentry

## Issue Reporting

Zendesk

Screen recording?

* [BugHerd](https://bugherd.com/our-features?utm\_expid=.H-YRVujJSBOhQkv6XBHqOg.1\&utm\_referrer=https%3A%2F%2Fbugherd.com%2F)

## Ssh

https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

```
ssh-keygen -t ed25519 -C "joshuayes@gmail.com"
```

## SSL

https://letsencrypt.org/

## Tmux

* https://tmuxcheatsheet.com/
* Source: https://gist.github.com/henrik/1967800

### Installation

https://linuxize.com/post/getting-started-with-tmux/#installing-tmux-on-macos

mac

```
brew install tmux
```

### Cheatsheet

As configured in [my dotfiles](https://github.com/henrik/dotfiles/blob/master/tmux.conf).

start new:

```
tmux
```

start new with session name:

```
tmux new -s myname
```

attach:

```
tmux a  #  (or at, or attach)
```

attach to named:

```
tmux a -t myname
```

list sessions:

```
tmux ls
```

kill session:

```
tmux kill-session -t myname
```

In tmux, hit the prefix `ctrl+b` and then:

### Sessions

Create session

```
tmux new -s hiiiike
```

List sessions

```
tmux ls
Ctrl + b s
```

### Windows (tabs)

```
c           new window
,           name window
w           list windows
f           find window
&           kill window
.           move window - prompted for a new number
:movew<CR>  move window to the next unused number
```

```
ctrl + b f
```

### Panes (splits)

ctrl b +\  
% horizontal split\  
" vertical split

```
o  swap panes
q  show pane numbers
x  kill pane
⍽  space - toggle between layouts
```

### Window/pane Surgery

```
:joinp -s :2<CR>  move window 2 into a new pane in the current window
:joinp -t :1<CR>  move the current pane into a new pane in window 1
```

* [Move window to pane](http://unix.stackexchange.com/questions/14300/tmux-move-window-to-pane)
* [How to reorder windows](http://superuser.com/questions/343572/tmux-how-do-i-reorder-my-windows)

### Misc

ctrl b +\  
d detach\  
t big clock\  
? list shortcuts\  
: prompt

Resources:

* [cheat sheet](http://cheat.errtheblog.com/s/tmux/)

Notes:

* You can cmd+click URLs to open in iTerm.

TODO:

* Conf copy mode to use system clipboard. See PragProg book.

### Search

ctrl b + \[\  
crtl s

```
n - next search match
? - search backward
/ - search forward
```

## Unix

`npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"`\  
`xargs`
