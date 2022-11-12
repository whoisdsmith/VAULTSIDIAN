# Bookmarklets Guide

[TOC2]

Bookmarklets are a simpler version of userscripts. They can be useful to extract some good stuff from websites.

## How to "install" and Use Them

1. Create a bookmark.
2. On the URL box, paste the script.
3. Go to the page you want to use the bookmarklet on.
4. Click on the bookmark (bookmarklet)

## Scripts

### General

#### Search and Highlight

```javascript:void%28s%3Dprompt%28%27Find text%3A%27%2C%27%27%29%29%3Bs%3D%27%28%27+s+%27%29%27%3Bx%3Dnew RegExp%28s%2C%27gi%27%29%3Brn%3DMath.floor%28Math.random%28%29*100%29%3Brid%3D%27z%27 + rn%3Bb %3D document.body.innerHTML%3Bb%3Db.replace%28x%2C%27<span name%3D%27 + rid + %27 id%3D%27 + rid + %27 style%3D%5C%27color%3A%23000%3Bbackground-color%3Ayellow%3B font-weight%3Abold%3B%5C%27>%241</span>%27%29%3Bvoid%28document.body.innerHTML%3Db%29%3Balert%28%27Found %27 + document.getElementsByName%28rid%29.length + %27 matches.%27%29%3Bwindow.scrollTo%280%2Cdocument.getElementsByName%28rid%29%5B0%5D.offsetTop%29%3B```  
[Source](https://gist.github.com/pdokas/711976)

#### Invert Lightness

```javascript:(function(){function RGBtoHSL(RGBColor){with(Math){var R,G,B;var cMax,cMin;var sum,diff;var Rdelta,Gdelta,Bdelta;var H,L,S;R=RGBColor[0];G=RGBColor[1];B=RGBColor[2];cMax=max(max(R,G),B);cMin=min(min(R,G),B);sum=cMax+cMin;diff=cMax-cMin;L=sum/2;if(cMax==cMin){S=0;H=0;}else{if(L<=(1/2))S=diff/sum;else S=diff/(2-sum);Rdelta=R/6/diff;Gdelta=G/6/diff;Bdelta=B/6/diff;if(R==cMax)H=Gdelta-Bdelta;else if(G==cMax)H=(1/3)+Bdelta-Rdelta;else H=(2/3)+Rdelta-Gdelta;if(H<0)H+=1;if(H>1)H-=1;}return[H,S,L];}}function getRGBColor(node,prop){var rgb=getComputedStyle(node,null).getPropertyValue(prop);var r,g,b;if(/rgb\((\d+),\s(\d+),\s(\d+)\)/.exec(rgb)){r=parseInt(RegExp.$1,10);g=parseInt(RegExp.$2,10);b=parseInt(RegExp.$3,10);return[r/255,g/255,b/255];}return rgb;}function hslToCSS(hsl){return "hsl("+Math.round(hsl[0]*360)+", "+Math.round(hsl[1]*100)+"%, "+Math.round(hsl[2]*100)+"%)";}var props=["color","background-color","border-left-color","border-right-color","border-top-color","border-bottom-color"];var props2=["color","backgroundColor","borderLeftColor","borderRightColor","borderTopColor","borderBottomColor"];if(typeof getRGBColor(document.documentElement,"background-color")=="string")document.documentElement.style.backgroundColor="white";revl(document.documentElement);function revl(n){var i,x,color,hsl;if(n.nodeType==Node.ELEMENT_NODE){for(i=0;x=n.childNodes[i];++i)revl(x);for(i=0;x=props[i];++i){color=getRGBColor(n,x);if(typeof(color)!="string"){hsl=RGBtoHSL(color);hsl[2]=1-hsl[2];n.style[props2[i]]=hslToCSS(hsl);}}}}})()```  
[Source](https://www.squarefree.com/bookmarklets/color.html)

#### X-Rays

```javascript: ( function () { const xray = document.createElement('style'); xray.innerHTML = "*{background:#000!important;color:#0f0!important;outline:solid%20#f00%201px!important;}%22;%20const%20xraysInPage%20=%20[…document.body.getElementsByTagName(%22style%22)].filter(style%20=%3E%20style.innerHTML%20===%20xray.innerHTML);%20if(xraysInPage.length%20%3E%200)%20{%20xraysInPage.forEach(style%20=%3E%20document.body.removeChild(style));%20}%20else%20{%20document.body.appendChild(xray)%20}%20}%20)();```  
[Source](https://www.reddit.com/r/bookmarklets/comments/ajmgx8/xray_a_little_browser_tool_that_i_wrote_that_i/)

### For Youtube

[Source](https://gbasil.dev/bookmarklets)

#### YouTube Thumbnail

```javascript:(()=>{ window.open(`https://img.youtube.com/vi/${new URLSearchParams(window.location.search).get("v")}/maxresdefault.jpg`); })();```

#### YouTube Audio Downloader

*(if it doesn't work, try refreshing the youtube page and click again)*  
```javascript:(async ()=>{ var ref, ref1; const playerResponse = ytplayer === null || ytplayer === void 0 ?%20void%200%20:%20(ref%20=%20ytplayer.config)%20===%20null%20||%20ref%20===%20void%200%20?%20void%200%20:%20(ref1%20=%20ref.args)%20===%20null%20||%20ref1%20===%20void%200%20?%20void%200%20:%20ref1.raw_player_response;%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20(!playerResponse)%20return%20alert(%22Error:%20Could%20not%20get%20player%20response%22);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20const%20escapeRegExp%20=%20(e)=%3Ee.replace(/[.*+?^${}()|[\]\\]/g,%20%22\\$&%22)%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20,%20parseDecsig%20=%20(data)=%3E{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20try%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20(data.startsWith(%22var%20script%22))%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20const%20obj%20=%20{},%20document%20=%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20createElement:%20()=%3Eobj%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20,%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20head:%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20appendChild:%20()=%3E{}%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20};%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20eval(data),%20data%20=%20obj.innerHTML;%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20const%20fnnameresult%20=%20/=([a-zA-Z0-9\$]+?)\(decodeURIComponent/.exec(data),%20fnname%20=%20fnnameresult[1],%20_argnamefnbodyresult%20=%20new%20RegExp(escapeRegExp(fnname)%20+%20%22=function\\((.+?)\\){((.+)=\\2.+?)}%22).exec(data),%20[_,%20argname,%20fnbody]%20=%20_argnamefnbodyresult,%20helpernameresult%20=%20/;(.+?)\..+?\(/.exec(fnbody),%20helpername%20=%20helpernameresult[1],%20helperresult%20=%20new%20RegExp(%22var%20%22%20+%20escapeRegExp(helpername)%20+%20%22={[\\s\\S]+?};%22).exec(data),%20helper%20=%20helperresult[0];%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20new%20Function([%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20argname%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20],%20helper%20+%20%22\n%22%20+%20fnbody);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20catch%20(e)%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20console.log(e),%20alert(%22Error:%20Could%20not%20parse%20signature%20decoder%22);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20},%20parseQuery%20=%20(e)=%3E[%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20…new%20URLSearchParams(e).entries()%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20].reduce((t,%20[a,%20r])=%3E(t[a]%20=%20r,%20t)%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20,%20{})%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20;%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20try%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20const%20e%20=%20parseDecsig(await%20(await%20fetch(document.querySelector(%27script[src$=%22base.js%22]%27).src)).text()),%20a%20=%20playerResponse.streamingData.adaptiveFormats.filter((n)=%3En.mimeType.startsWith(%22audio/%22)%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20).sort((n,%20s)=%3En.bitrate%20%3C%20s.bitrate%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20)[0],%20r%20=%20parseQuery(a.signatureCipher);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20open(a.url%20||%20`${r.url}&${r.sp}=${e(r.s)}`);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20catch%20(e)%20{%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20console.log(e),%20alert(%22Error:%20An%20unknown%20error%20ocurred%20in%20the%20main%20process%22);%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20}%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20})();```

### For Open Directories

[Source](https://www.reddit.com/r/opendirectories/comments/933pzm/all_resources_i_know_related_to_open_directories/)

#### Display Pictures as Thumbnails

```javascript:(function(){function%20I(u){var%20t=u.split('.'),e=t[t.length-1].toLowerCase();return%20{gif:1,jpg:1,jpeg:1,png:1,mng:1}[e]}function%20hE(s){return%20s.replace(/&/g,'&amp;').replace(/>/g,'>').replace(/</g,'<').replace(/"/g,'&quot;');}var%20q,h,i,z=open().document;z.write('<p>Images%20linked%20to%20by%20'+hE(location.href)+':</p><hr>');for(i=0;q=document.links[i];++i){h=q.href;if(h&&I(h))z.write('<p>'+q.innerHTML+'%20('+hE(h)+')<br><img%20src="'+hE(h)+'">');}z.close();})()```

#### Display Pictures as Thumbnail Gallery

```javascript:var%20sHTML=%22<html><head><title>gallery</title><body><center><table%20border=0>%22;var%20y=0;for(x=0;x<document.links.length;x++){a=document.links[x].href;%20if%20(a.match(/jpe|jpeg|jpg|bmp|tiff|tif|bmp|gif|png/i)){sHTML+='<td%20style=%22border-style:solid;border-width:1px%22><a%20target=%22_new%22%20href=%22'+a+'%22><img%20border=%220%22%20width=%22100%22%20src=%22'+a+'%22></a></td>';%20if%20(!((x+1)%5))%20sHTML+=%22</tr><tr>%22}};this.innerHTML=sHTML+%22</table></center></body></html>%22;```

#### Resize File Names

```javascript:!function(){function e(e){var o,n,r=e.href;e.textContent=(n=(o=r).split("/").filter(Boolean).reverse()[0],console.log(n),o.lastIndexOf("/")==o.lenght-1&&(n+="/"),n=n.indexOf(" ")>=0?decodeURI(n):decodeURIComponent(n))}anchors=document.body.querySelectorAll(%22a%22),anchors=Array.from(anchors).slice(1),anchors.map(e)}();```

## Extra Resources

- [Jesse's Bookmarklets Site](https://www.squarefree.com/bookmarklets/)
- [gbasil.dev](https://gbasil.dev/bookmarklets)
- [r/Bookmarklets - Top posts](https://www.reddit.com/r/bookmarklets/top/?t=all)
- [Osint-Bookmarklets](https://github.com/B0sintBlanc/Osint-Bookmarklets)
- [Subsimple Navigation Bookmarklets](https://subsimple.com/bookmarklets/collection_navigation.php)

*Credits: [Rust1667](https://github.com/Rust1667)*
