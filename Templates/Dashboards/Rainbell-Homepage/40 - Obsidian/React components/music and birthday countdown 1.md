---
defines-react-components: true
---

# music and birthday countdown 1

```jsx:component:ShowI

const files = app.vault.getMarkdownFiles();
let count = 0;
let final = "";
let cells = [];

for (var ita=0;ita<files.length;ita++){
 let today = new Date();
 let year = today.getFullYear();
 let yearString = year.toString();
 const basename = files[ita].basename;
 
 const meta = app.metadataCache.getFileCache(files[ita]).frontmatter;
 if (typeof(meta) != "undefined"){
  const birthday = app.metadataCache.getFileCache(files[ita]).frontmatter.birthday;
  if (birthday){
   let birthdaySlice = birthday.slice(4);
   let nextBirthdayString = yearString+birthdaySlice;
   let birthdayMonth = birthday.slice(5,7);
   let birthdayDay = birthday.slice(8,10);
   if (birthdayMonth.slice(0,1)==0){
    birthdayMonth = birthdayMonth.slice(1);
   } 
   if (birthdayDay.slice(0,1)==0){
    birthdayDay = birthdayDay.slice(1);
   } 
   let hanBirthday = birthdayMonth + "月" + birthdayDay + "日";
   let nextBirthdayNumber = new Date(nextBirthdayString);
   let diffBetween = Math.floor((nextBirthdayNumber-today)/3600000/24);
   let N = 0;
   diffBetween>=0? N = diffBetween:N = diffBetween+365;
   if (N < 31){
    count = count+1;
    cells.push(<div class = "birdcountdown">  <text class = "birdname"> {basename}'s Birthday </text><text class="countdowndays"> {N+1} days </text></div>) 
   }
  }
 }
}

const element = <div>{count} birthdays in the following month: <br /> </div>;

const div3Style = {
  frameborder:"no", 
  border:"0",
  marginwidth:"0",
  marginheight:"0",
  width:330,
  height:110,
}
   

return (
 <div class="musicBirthday">
 
  <div style={{flex: 1, textAlign: 'center', whiteSpace: 'pre-wrap'}}>
   <p><b>MUSIC OF THE MONTH</b></p>
   <iframe  style={div3Style}  src="https://music.163.com/outchain/player?type=0&id=7354648923&auto=0&height=90"></iframe>
  </div>
  <div style={{flex: 1, textAlign: 'center', whiteSpace: 'pre-wrap'}}>
   <p><b>UPCOMING BIRTHDAYS</b></p>
   <p>{element}{cells} </p>
  </div>
 </div>
)


```

```jsx:
<ShowI></ShowI>
```

  final +=  <div> {basename}生日在 {hanBirthday}，还有 {N+1} 天 </div> 
  
      cells.push(<div class = "birdcountdown">  <text class = "birdname"> {basename} </text>生日在 <text class = "birdbirthday">{hanBirthday}</text>，还有<text class="countdowndays"> {N+1} </text> 天 </div>) 
