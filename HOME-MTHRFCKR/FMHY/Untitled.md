# Extensions and Scripts

[TOC]

##Info
**More guides and Links - https://rentry.co/Mega-Rentry**
This Guide has Extensions and Scripts that Pirates should use
IT IS NOT A COMPLETE LIST

## Extensions 
### AdBlock
Refer to AdBlocker Section at https://rentry.co/MR-Extensions-Script#adblocker
### ClearURLs
Remove Trackers from URLs
https://gitlab.com/KevinRoebert/ClearUrls
### UniversalBypass 
Bypass Link Shortners
https://universal-bypass.org/
### ViolentMonkey
Open Source Scripting Extension
https://violentmonkey.github.io/

## Scripts
### SiteScrubber
Project intended to make QOL scripts to scrub a list of file-hosting sites downloading pages to make life simpler.

SiteScrubber is specifically made for various download sites that have you wait a certain amount of time, or click a button that is buried behind invisible blocks that intercept your click and take you to a different site. These scripts will help remove all the clutter and make the page simple to navigate and complete to download your requested files!
Useful for Mobilism Users

https://github.com/PrimePlaya24/dl-site-scrubber

### AdsBypasser 
Skip countdown ads or continue pages and prevent ad pop-up windows.
https://adsbypasser.github.io

### Mega Unlimited Import
Bypass Import Restriction on Mega account (Need to have free space to Import)
No Proper Page, Script code at End of Rentry
https://rentry.co/MR-Extensions-Script#mega-script

### Symbolab View Steps
Just sign into any account and you will be able yo view the Steps to Solution on Symbolab
No Proper Page, Script code at End of Rentry
https://rentry.co/MR-Extensions-Script#mega-script

### Aternos Anti-AdBlock
Removes / Bypasses the Waiting page for AdBlock users on Aternos (Minecraft Server Host)
No Proper Page, Script code at End of Rentry
https://rentry.co/MR-Extensions-Script#aternos-script

### Auto Solve hCaptchas 
Uses TesnorFlow to solve
Edited script posted to remove the referal ads
https://rentry.co/MR-Extensions-Script#hcaptcha-script

### Auto Solve Google reCaptchas 
Uses TesnorFlow to solve
Edited script posted to remove the referal ads
https://rentry.co/MR-Extensions-Script#recaptcha-script

##AdBlocker
### The One To Use
It should be no Surprise that here we have linked uBlock Origin
https://github.com/gorhill/uBlock#ublock-origin
It is the Blocker to use. Opinions may vary but its what majority of the Community seems to prefer and recommend

### Lists to Add
Though, uBO gives a lot of in-Built lists, here are some more too add

####Fuck FuckAdBlock (Must add)
https://raw.githubusercontent.com/bogachenko/fuckfuckadblock/master/fuckfuckadblock.txt

Mirrors - 
https://raw.githack.com/bogachenko/fuckfuckadblock/master/fuckfuckadblock.txt
https://cdn.statically.io/gh/bogachenko/fuckfuckadblock/master/fuckfuckadblock.txt
https://cdn.jsdelivr.net/gh/bogachenko/fuckfuckadblock/fuckfuckadblock.txt

#### WebAnnoyances 
Hides the Annoying Banners and other junk on sites
https://raw.githubusercontent.com/yourduskquibbles/webannoyances/master/ultralist.txt&title=Web%20Annoyances%20Ultralist

#### Filter Stalker Lists
To use, simply select "import" in uBlock's filter tab and paste the following links: 

https://openphish.com/feed.txt
https://raw.githubusercontent.com/easylist/easylist/master/fanboy-addon/fanboy_notifications_general_block.txt
https://raw.githubusercontent.com/easylist/easylist/master/fanboy-addon/fanboy_notifications_general_hide.txt
https://raw.githubusercontent.com/easylist/easylist/master/fanboy-addon/fanboy_notifications_thirdparty.txt
https://filters.adtidy.org/extension/ublock/filters/1.txt
https://raw.githubusercontent.com/hant0508/uBlock-filters/master/filters.txt
https://raw.githubusercontent.com/bogachenko/fuckfuckadblock/master/fuckfuckadblock.txt
https://raw.githubusercontent.com/piperun/iploggerfilter/master/filterlist
https://raw.githubusercontent.com/IDKwhattoputhere/uBlock-Filters-Plus/master/uBlock-Filters-Plus.txt
https://raw.githubusercontent.com/yourduskquibbles/webannoyances/master/filters/modal_filters.txt
https://raw.githubusercontent.com/yourduskquibbles/webannoyances/master/filters/newsletter_filters.txt
https://raw.githubusercontent.com/nimasaj/uBOPa/master/uBOPa.txt
https://raw.githubusercontent.com/metaphoricgiraffe/tracking-filters/master/trackingfilters.txt
https://zerodot1.gitlab.io/CoinBlockerLists/list_browser_UBO.txt 

### Some Custom Filters


## Script Codes
### Mega-Script
```
// ==UserScript==
// @name         MEGA.nz Ultimately Import
// @name:zh-TW   MEGA.nz Ultimately Import /
// @name:zh-CN   MEGA.nz Ultimately Import 
// @namespace    methusela
// @version      1.0
// @description  Bypass import limit on Mega Web client & remove warning about the space usage
// @author       Mega-Rentry Project
// @match        chrome-extension://bigefpfhnfcobdlfbedofhhaibnlghod/*
// @match        http://mega.co.nz/*
// @match        http://mega.io/*
// @match        http://mega.is/*
// @match        http://mega.nz/*
// @match        https://mega.co.nz/*
// @match        https://mega.io/*
// @match        https://mega.is/*
// @match        https://mega.nz/*
// @icon         https://mega.nz/favicon.ico?v=3
// @run-at       document-end
// @grant        none
// ==/UserScript==

(function() {
    'use strict';
    // Reference [Augular loaded detect]: https://stackoverflow.com/a/31970556/9182265
    var initWatcher = setInterval(function () {
        if (window.MegaUtils) {
            clearInterval(initWatcher);
            hookImport();
            hookFull();
            console.info('FUNtions Hooked!');
        }
    }, 500);
})();

var hookImport = function () {
    MegaUtils.prototype.checkGoingOverStorageQuota = function(opSize) {
        var promise = new MegaPromise();
        loadingDialog.pshow();

        M.getStorageQuota()
            .always(function() {
            loadingDialog.phide();
        })
            .fail(promise.reject.bind(promise))
            .done(function(data) {

            /*
            if (opSize === -1) {
                opSize = data.mstrg;
            }

            if (opSize %3E data.mstrg - data.cstrg) {
                var options = {custom: 1, title: l[882], body: l[16927]};

                M.showOverStorageQuota(data, options)
                    .always(function() {
                    promise.reject();
                });
            }
            else {
            */
            promise.resolve();
        });
        return promise;
    };
}

var hookFull = function () {
    FileManager.prototype.showOverStorageQuota = null;
}
```

### Aternos-Script
```
// ==UserScript==
// @name        Aternos anti-anti adblock
// @description Kills Aternos' annoying full-page + timeout anti-adblock.
// @version     1.0.3
// @author      Lucy
// @copyright   2021, Lucy (absolucy.moe)
// @license     BSD-3-Clause; https://github.com/Absolucy/userscripts/blob/dev/LICENSE.md
// @downloadURL https://cdn.jsdelivr.net/gh/Absolucy/userscripts@dev/scripts/AternosAntiAntiAdblock.user.js
// @updateURL   https://cdn.jsdelivr.net/gh/Absolucy/userscripts@dev/scripts/AternosAntiAntiAdblock.user.js
// @source      https://github.com/Absolucy/userscripts
// @namespace   https://github.com/Absolucy
// @match       *://aternos.org/*
// @grant       none
// @inject-into page
// @run-at      document-start
// @meta        Trans rights are human rights.
// @meta        If you disagree with that, you have every right to fuck off and not use my scripts :)
// ==/UserScript==

const regex = /function ([A-Za-z]+)\(\)\s+\{\s+([A-Za-z]+)\s+\=\s*true\s*;\s*([A-Za-z]+)\(\)\s*;\s*}\s*let\s*[a-zA-Z],\s*[a-zA-Z]\s*;/;

(function () {
	"use strict";
	let old_atob = unsafeWindow.atob;
	unsafeWindow.atob = function (i) {
		let out = old_atob(i);
		unsafeWindow.console.log("Decoded: " + out);
		let find_function = regex.exec(out);
		if (find_function) {
			let function_name = find_function[1];
			unsafeWindow.console.log(
				"Patching " + function_name + " to 'Function.prototype'"
			);
			out = out.replace(function_name, "Function.prototype");
			unsafeWindow.console.log("Patched: " + out);
		}
		return out.replace(
			".addClass('fa-sad-tear');",
			".addClass('fa-sad-tear'); return true;"
		);
	};
})();

```

### Symbolab-Script
```
// ==UserScript==
// @name         Unlock locked steps in Symbolab
// @namespace    http://*.symbolab.com/*
// @version      1.0
// @description  unlocks locked symbolab step-by-step instructions by overwriting XMLHttpRequest
// @author       Mega-Rentry Project
// @match        *://*.symbolab.com/*
// @grant        none
// ==/UserScript==

(function(open) {
    
    var patched = 0;
    var signedIn = true;
    var shownAlert = false;
    
    let NOT_SIGNED_IN_MESSAGE = "[Symbolab Unlock] ALERT! It looks like you are not logged into any Symbolab account. Note that Symbolab has recently changed their backend and steps are only sent if you are logged in. The script will not work until you create a free Symbolab account and sign in to it. If you are signed in, ignore this message.";

    function patchResponseLoop(obj) {
        for (var k in obj)
        {
            if (typeof obj[k] == "object" && obj[k] !== null) {
                patchResponseLoop(obj[k]);
            } else {
                if (k == "isLocked") {
                    obj[k] = false;
                    console.log("[patcher] patched a symbolab isLocked property");
                    patched++;
                }
            }
        }
    }

    var open_prototype = XMLHttpRequest.prototype.open,
        intercept_response = function(urlpattern, callback) {
            XMLHttpRequest.prototype.open = function() {
                arguments['1'].match(urlpattern) && this.addEventListener('readystatechange', function(event) {
                    if ( this.readyState === 4 ) {
                        var response = callback(event.target.responseText);
                        // allow intercepted responses to be written to
                        Object.defineProperty(this, 'response', {writable: true});
                        Object.defineProperty(this, 'responseText', {writable: true});

                        this.response = this.responseText = response;
                    }
                });
                return open_prototype.apply(this, arguments);
            };
        };

    if (signedIn) {
        intercept_response(/steps/i, function(response) {
            console.log("[patcher] intercept request, current RES ", JSON.parse(response));

            var parsedO = JSON.parse(response);

            patchResponseLoop(parsedO);

            console.log("[patcher] === PATCHSET COMPLETE, enjoy ===");
            document.getElementById("PlotLink").innerHTML = "%3Cb>Unlocked " + patched + " step(s)!</b>";
    
            return JSON.stringify(parsedO);
        });
    } else {
        document.getElementById("PlotLink").innerHTML = "<b>Please sign in to Symbolab to unlock steps.</b>";
    }
    // tell the user that the script will not work unless they are
    // signed into a free account
    
    if (document.getElementsByClassName("signedin").length < 5 && !document.getElementById("warning_text_symbolab_unlock")) { // hacky way to determine whether logged in
        signedIn = false;
        
        // Determine where we should place the alert
        referenceNode = document.getElementById("nl-mainNav");
        
        /**<div style="border: 1px solid #f00; width:60%; margin: 0 auto;">
<b style="color:red;">[Symbolab Unlock] ALERT! It looks like you are not logged into any Symbolab account. Note that Symbolab has recently changed their backend and steps are only sent if you are logged in. The script will not work until you create a free Symbolab account and sign in to it. If you are signed in, ignore this message.</b>

</div>*/
        
        // Create warning div
        warningDiv = document.createElement("div");
        warningDiv.style.border = "1px solid #f00";
        warningDiv.style.width = "60%";
        warningDiv.style.margin = "0 auto";
        warningDiv.id = "warning_text_symbolab_unlock"
        
        // Create warning text
        warningTxt = document.createElement("b");
        warningTxt.appendChild(document.createTextNode(NOT_SIGNED_IN_MESSAGE))
        warningTxt.style.color = "red";
        
        // Append text to div
        warningDiv.appendChild(warningTxt);
        
        // Append div to page
        referenceNode.parentNode.insertBefore(warningDiv, referenceNode.nextSibling);
    }

})(XMLHttpRequest.prototype.open);
```

### recaptcha-script
```
// ==UserScript==
// @name         Recaptcha Solver (Automatically solves Recaptcha in browser)
// @namespace    Recaptcha Solver
// @version      1.0
// @description  Recaptcha Solver in Browser | Automatically solves Recaptcha in browser
// @author       MegaRentry ReHost
// @match        *://*/recaptcha/api2/*
// @connect      engageub.pythonanywhere.com
// @grant        GM_xmlhttpRequest
/*

██████╗ ███████╗ ██████╗ █████╗ ██████╗ ████████╗ ██████╗██╗  ██╗ █████╗     ███████╗ ██████╗ ██╗    ██╗   ██╗███████╗██████╗
██╔══██╗██╔════╝██╔════╝██╔══██╗██╔══██╗╚══██╔══╝██╔════╝██║  ██║██╔══██╗    ██╔════╝██╔═══██╗██║    ██║   ██║██╔════╝██╔══██╗
██████╔╝█████╗  ██║     ███████║██████╔╝   ██║   ██║     ███████║███████║    ███████╗██║   ██║██║    ██║   ██║█████╗  ██████╔╝
██╔══██╗██╔══╝  ██║     ██╔══██║██╔═══╝    ██║   ██║     ██╔══██║██╔══██║    ╚════██║██║   ██║██║    ╚██╗ ██╔╝██╔══╝  ██╔══██╗
██║  ██║███████╗╚██████╗██║  ██║██║        ██║   ╚██████╗██║  ██║██║  ██║    ███████║╚██████╔╝███████╗╚████╔╝ ███████╗██║  ██║
╚═╝  ╚═╝╚══════╝ ╚═════╝╚═╝  ╚═╝╚═╝        ╚═╝    ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝    ╚══════╝ ╚═════╝ ╚══════╝ ╚═══╝  ╚══════╝╚═╝  ╚═╝
/*


/** Note: This script is solely intended for the use of educational purposes only and not to abuse any website.
This script uses audio in order to solve the captcha. Use it wisely and do not abuse any website.
*/
// ==/UserScript==
(function() {
    'use strict';
    var solved = false;
    var checkBoxClicked = false;
    var waitingForAudioResponse = false;
    //Node Selectors
    const CHECK_BOX = ".recaptcha-checkbox-border";
    const AUDIO_BUTTON = "#recaptcha-audio-button";
    const PLAY_BUTTON = ".rc-audiochallenge-play-button .rc-button-default";
    const AUDIO_SOURCE = "#audio-source";
    const IMAGE_SELECT = "#rc-imageselect";
    const RESPONSE_FIELD = ".rc-audiochallenge-response-field";
    const AUDIO_ERROR_MESSAGE = ".rc-audiochallenge-error-message";
    const AUDIO_RESPONSE = "#audio-response";
    const RELOAD_BUTTON = "#recaptcha-reload-button";
    const RECAPTCHA_STATUS = "#recaptcha-accessible-status";
    const DOSCAPTCHA = ".rc-doscaptcha-body";
    const VERIFY_BUTTON = "#recaptcha-verify-button";
    const MAX_ATTEMPTS = 5;
    var requestCount = 0;
    var recaptchaLanguage = qSelector("html").getAttribute("lang");
    var audioUrl = "";
    var recaptchaInitialStatus = qSelector(RECAPTCHA_STATUS) ? qSelector(RECAPTCHA_STATUS).innerText : ""
    //Check for visibility && Click the check box
    function isHidden(el) {
        return(el.offsetParent === null)
    }

    async function getTextFromAudio(URL) {
        requestCount = requestCount + 1;
        URL = URL.replace("recaptcha.net", "google.com");
        if(recaptchaLanguage.length < 1) {
            console.log("Recaptcha Language is not recognized");
            recaptchaLanguage = "en-US";
        }
        console.log("Recaptcha Language is " + recaptchaLanguage);
        GM_xmlhttpRequest({
            method: "POST",
            url: "https://engageub.pythonanywhere.com",
            headers: {
                "Content-Type": "application/x-www-form-urlencoded"
            },
            data: "input=" + encodeURIComponent(URL) + "&lang=" + recaptchaLanguage,
            timeout: 15000,
            onload: function(response) {
                console.log("Response::" + response.responseText);
                try {
                    if(response && response.responseText) {
                        var responseText = response.responseText;
                        //Validate Response for error messages or html elements
                        if(responseText == "0" || responseText.includes("<") || responseText.includes(">") || responseText.length < 2 || responseText.length > 50) {
                            //Invalid Response, Reload the captcha
                            console.log("Invalid Response. Retrying..");
                        } else if(qSelector(AUDIO_SOURCE) && qSelector(AUDIO_SOURCE).src && audioUrl == qSelector(AUDIO_SOURCE).src && qSelector(AUDIO_RESPONSE)
                                  && !qSelector(AUDIO_RESPONSE).value && qSelector(AUDIO_BUTTON).style.display == "none" && qSelector(VERIFY_BUTTON)) {
                            qSelector(AUDIO_RESPONSE).value = responseText;
                            qSelector(VERIFY_BUTTON).click();
                        } else {
                            console.log("Could not locate text input box")
                        }
                        waitingForAudioResponse = false;
                    }

                } catch(err) {
                    console.log(err.message);
                    console.log("Exception handling response. Retrying..");
                    waitingForAudioResponse = false;
                }
            },
            onerror: function(e) {
                console.log(e);
                waitingForAudioResponse = false;
            },
            ontimeout: function() {
                console.log("Response Timed out. Retrying..");
                waitingForAudioResponse = false;
            },
        });
    }

    function qSelectorAll(selector) {
        return document.querySelectorAll(selector);
    }

    function qSelector(selector) {
        return document.querySelector(selector);
    }

    //Solve the captcha using audio
    var startInterval = setInterval(function() {
        try {
            if(!checkBoxClicked && qSelector(CHECK_BOX) && !isHidden(qSelector(CHECK_BOX))) {
                //console.log("checkbox clicked");
                qSelector(CHECK_BOX).click();
                checkBoxClicked = true;
            }
            //Check if the captcha is solved
            if(qSelector(RECAPTCHA_STATUS) && (qSelector(RECAPTCHA_STATUS).innerText != recaptchaInitialStatus)) {
                solved = true;
                console.log("SOLVED");
                clearInterval(startInterval);
            }
            if(requestCount > MAX_ATTEMPTS) {
                console.log("Attempted Max Retries. Stopping the solver");
                solved = true;
                clearInterval(startInterval);
            }
            if(!solved) {
                if(qSelector(AUDIO_BUTTON) && !isHidden(qSelector(AUDIO_BUTTON)) && qSelector(IMAGE_SELECT)) {
                    // console.log("Audio button clicked");
                    qSelector(AUDIO_BUTTON).click();
                }
                if((!waitingForAudioResponse && qSelector(AUDIO_SOURCE) && qSelector(AUDIO_SOURCE).src
                    && qSelector(AUDIO_SOURCE).src.length > 0 && audioUrl == qSelector(AUDIO_SOURCE).src
                    && qSelector(RELOAD_BUTTON)) ||
                   (qSelector(AUDIO_ERROR_MESSAGE) && qSelector(AUDIO_ERROR_MESSAGE).innerText.length > 0 && qSelector(RELOAD_BUTTON))){
                    qSelector(RELOAD_BUTTON).click();
                } else if(!waitingForAudioResponse && qSelector(RESPONSE_FIELD) && !isHidden(qSelector(RESPONSE_FIELD))
                          && !qSelector(AUDIO_RESPONSE).value && qSelector(AUDIO_SOURCE) && qSelector(AUDIO_SOURCE).src
                          && qSelector(AUDIO_SOURCE).src.length > 0 && audioUrl != qSelector(AUDIO_SOURCE).src
                          && requestCount <= MAX_ATTEMPTS) {
                    waitingForAudioResponse = true;
                    audioUrl = qSelector(AUDIO_SOURCE).src
                    getTextFromAudio(audioUrl);
                }else {
                    //Waiting
                }
            }
            //Stop solving when Automated queries message is shown
            if(qSelector(DOSCAPTCHA) && qSelector(DOSCAPTCHA).innerText.length > 0) {
                console.log("Automated Queries Detected");
                clearInterval(startInterval);
            }
        } catch(err) {
            console.log(err.message);
            console.log("An error occurred while solving. Stopping the solver.");
            clearInterval(startInterval);
        }
    }, 5000);

})();
```

### hcaptcha-script
```
// ==UserScript==
// @name         Hcaptcha Solver (Automatically solves Hcaptcha in browser)
// @namespace    Hcaptcha Solver
// @version      1.0
// @description  Hcaptcha Solver in Browser | Automatically solves Hcaptcha in browser
// @author       Mega Rentry ReHost
// @match        *://*.hcaptcha.com/*hcaptcha-challenge*
// @match        *://*.hcaptcha.com/*checkbox*
// @grant        GM_xmlhttpRequest
// @connect      www.imageidentify.com
// @connect      https://cdnjs.cloudflare.com
// @connect      https://cdn.jsdelivr.net
// @connect      https://unpkg.com
// @connect      *://*.hcaptcha.com/*
// @require      https://unpkg.com/jimp@0.5.2/browser/lib/jimp.min.js
// @require      https://cdnjs.cloudflare.com/ajax/libs/tesseract.js/2.0.0-alpha.2/tesseract.min.js
// @require      https://cdn.jsdelivr.net/npm/@tensorflow/tfjs/dist/tf.min.js
// @require      https://cdn.jsdelivr.net/npm/@tensorflow-models/coco-ssd


/*
██╗░░██╗░█████╗░░█████╗░██████╗░████████╗░█████╗░██╗░░██╗░█████╗░  ░██████╗░█████╗░██╗░░░░░██╗░░░██╗███████╗██████╗░
██║░░██║██╔══██╗██╔══██╗██╔══██╗╚══██╔══╝██╔══██╗██║░░██║██╔══██╗  ██╔════╝██╔══██╗██║░░░░░██║░░░██║██╔════╝██╔══██╗
███████║██║░░╚═╝███████║██████╔╝░░░██║░░░██║░░╚═╝███████║███████║  ╚█████╗░██║░░██║██║░░░░░╚██╗░██╔╝█████╗░░██████╔╝
██╔══██║██║░░██╗██╔══██║██╔═══╝░░░░██║░░░██║░░██╗██╔══██║██╔══██║  ░╚═══██╗██║░░██║██║░░░░░░╚████╔╝░██╔══╝░░██╔══██╗
██║░░██║╚█████╔╝██║░░██║██║░░░░░░░░██║░░░╚█████╔╝██║░░██║██║░░██║  ██████╔╝╚█████╔╝███████╗░░╚██╔╝░░███████╗██║░░██║
╚═╝░░╚═╝░╚════╝░╚═╝░░╚═╝╚═╝░░░░░░░░╚═╝░░░░╚════╝░╚═╝░░╚═╝╚═╝░░╚═╝  ╚═════╝░░╚════╝░╚══════╝░░░╚═╝░░░╚══════╝╚═╝░░╚═╝
*/
/** Note: This script is solely intended for the use of educational purposes only and not to abuse any website.
*/

// ==/UserScript==
(function() {

    //TODO: Enable debug mode to print console logs
    'use strict';
    var selectedImageCount = 0;
    var tensorFlowModel = undefined;
    var worker = undefined;


    //Node Selectors
    const CHECK_BOX = "#checkbox";
    const SUBMIT_BUTTON = ".button-submit";
    const TASK_IMAGE_BORDER = ".task-image .border";
    const IMAGE = ".task-image .image";
    const TASK_IMAGE = ".task-image";
    const PROMPT_TEXT = ".prompt-text";
    const NO_SELECTION = ".no-selection";
    const CHALLENGE_INPUT_FIELD = ".challenge-input .input-field";
    const CHALLENGE_INPUT = ".challenge-input";
    const IMAGE_FOR_OCR = ".challenge-image .zoom-image";

    //Attributes
    const ARIA_CHECKED = "aria-checked";
    const ARIA_HIDDEN = "aria-hidden";

    //Values that can be changed for other languages
    const AIRPLANE = "airplane";
    const BICYCLE = "bicycle";
    const BOAT = "boat";
    const CAR = "car";
    const MOTORBUS = "motorbus";
    const MOTORCYCLE = "motorcycle";
    const TRAIN = "train";
    const TRUCK = "truck";
    const TRANSPORT_TYPES = [AIRPLANE, BICYCLE, BOAT, CAR, MOTORBUS, MOTORCYCLE, TRAIN, TRUCK];

    const SENTENCE_TEXT_A = "Please click each image containing a ";
    const SENTENCE_TEXT_AN = "Please click each image containing an ";
    const LANGUAGE_FOR_OCR = "eng";

    // Option to override the default image matching
    const ENABLE_TENSORFLOW = false;

    String.prototype.includesOneOf = function(arrayOfStrings) {

        //If this is not an Array, compare it as a String
        if (!Array.isArray(arrayOfStrings)) {
            return this.toLowerCase().includes(arrayOfStrings.toLowerCase());
        }

        for (var i = 0; i < arrayOfStrings.length; i++) {
            if ((arrayOfStrings[i].substr(0, 1) == "=" && this.toLowerCase() == arrayOfStrings[i].substr(1).toLowerCase()) ||
                (this.toLowerCase().includes(arrayOfStrings[i].toLowerCase()))) {
                return true;
            }
        }
        return false;
    }


    // This script uses imageidentify API (wolfram) . You may also use TensorFlow.js, Yolo latest version to recognize common objects.
    //(When the cloud service is available for yolo, we can switch the API endpoint). Accuracy varies between Wolfram, Tensorflow and Yolo.
    // Use this as a reference to solve recaptcha/other captchas using scripts in browser. This is intended for learning purposes.
    // Using TensorFlow as fallback, but this requires good CPU in order to solve quickly.
    // CPU utilization and memory utlization may go high when using TensorFlow.js
    function matchImages(imageUrl, word, i) {

        GM_xmlhttpRequest({
            method: "POST",
            url: "https://www.imageidentify.com/objects/user-26a7681f-4b48-4f71-8f9f-93030898d70d/prd/urlapi/",
            headers: {
                "Content-Type": "application/x-www-form-urlencoded"
            },
            data: "image=" + encodeURIComponent(imageUrl),
            timeout: 8000,
            onload: function(response) {
                clickImages(response, imageUrl, word, i)
            },
            onerror: function(e) {
                //Using Fallback TensorFlow
                console.log(e);
                console.log("Using Fallback");
                matchImagesUsingTensorFlow(imageUrl, word, i);

            },
            ontimeout: function() {
                console.log("Timed out. Using Fallback");
                matchImagesUsingTensorFlow(imageUrl, word, i);
            },
        });

    }

    function matchImagesUsingTensorFlow(imageUrl, word, i) {
        try {
            var img = new Image();
            img.crossOrigin = "Anonymous";
            img.src = imageUrl;
            img.onload = () => {
                initializeTensorFlowModel().then(model => model.detect(img))
                    .then(function(predictions) {
                    var predictionslen = predictions.length;
                    for (var j = 0; j < predictionslen; j++) {
                        if (qSelectorAll(IMAGE)[i] && (qSelectorAll(IMAGE)[i].style.background).includes(imageUrl) &&
                            qSelectorAll(TASK_IMAGE_BORDER)[i].style.opacity == 0 &&
                            predictions[j].class.includesOneOf(word)) {
                            qSelectorAll(TASK_IMAGE)[i].click();
                            break;
                        }
                    }
                    selectedImageCount = selectedImageCount + 1;
                });
            }
        } catch (err) {
            console.log(err.message);
        }
    }

    //Different Models can be set later based on usecase
    //Ref Models: https://github.com/tensorflow/tfjs-models
    async function initializeTensorFlowModel() {
        if (!tensorFlowModel) {
            tensorFlowModel = await cocoSsd.load();
        }
        return tensorFlowModel;
    }

    //Initialize TesseractWorker
    function initializeTesseractWorker() {
        if(!worker){
            worker = new Tesseract.TesseractWorker();
        }
    }

    function clickImages(response, imageUrl, word, i) {

        try {
            if (response && response.responseText && (qSelectorAll(IMAGE)[i].style.background).includes(imageUrl) && qSelectorAll(TASK_IMAGE_BORDER)[i].style.opacity == 0) {
                var responseJson = JSON.parse(response.responseText);
                if (responseJson.identify && responseJson.identify.title && responseJson.identify.title.includesOneOf(word)) {
                    qSelectorAll(TASK_IMAGE)[i].click();
                } else if (responseJson.identify && responseJson.identify.entity && responseJson.identify.entity.includesOneOf(word)) {
                    qSelectorAll(TASK_IMAGE)[i].click();
                } else if (responseJson.identify && responseJson.identify.alternatives) {
                    var alternatives = JSON.stringify(responseJson.identify.alternatives);
                    var alternativesJson = JSON.parse(alternatives);

                    for (var key in alternativesJson) {
                        if (alternativesJson.hasOwnProperty(key)) {
                            if ((alternativesJson[key].includesOneOf(word) || key.includesOneOf(word))) {
                                qSelectorAll(TASK_IMAGE)[i].click();
                                break;
                            }
                        }
                    }
                } else {
                    //No Match found
                }

                selectedImageCount = selectedImageCount + 1;

            } else {
                console.log("Using Fallback TensorFlow");
                matchImagesUsingTensorFlow(imageUrl, word, i);
            }

        } catch (err) {
            //Using Fallback TensorFlow
            console.log(err.message);
            console.log("Using Fallback TensorFlow");
            matchImagesUsingTensorFlow(imageUrl, word, i);
        }
    }

    function qSelectorAll(selector) {
        return document.querySelectorAll(selector);
    }

    function qSelector(selector) {
        return document.querySelector(selector);
    }


    async function getSynonyms(word) {

        //TODO: Format this to JSON string
        var tempWord = word;

        if (!tempWord.includesOneOf(TRANSPORT_TYPES)) {
            console.log("New word or different cyrillic");
            var img = await convertTextToImage(word);
            tempWord = await convertImageToText(img);
            img.removeAttribute("src");
            word = tempWord;
        }

        if (word == MOTORBUS) {
            word = ['bus', 'motorbus'];
        } else if (word == CAR) {
            word = ['=car', 'coupe', 'jeep', 'limo', 'sport utility vehicle', 'station wagon', 'hatchback', 'bumper car', 'modelT', 'electric battery', 'cruiser'];
        } else if (word == AIRPLANE) {
            word = ['airplane', 'plane', 'aircraft', 'aeroplane', 'hangar', 'Airdock', 'JumboJet', 'jetliner', 'stealth fighter', 'field artillery']
        } else if (word == TRAIN) {
            word = ['train', 'rail', 'cable car', 'locomotive', 'subway station']
        } else if (word == BOAT) {
            word = ['=boat', '=barge', 'houseboat', 'bobsled', 'pontoon', 'small boat', 'SnowBlower', 'Sea-coast', 'PaddleSteamer', 'Freighter', 'Sternwheeler', 'kayak', 'canoe', 'deck', 'DockingFacility', 'surfboard', 'ship', '=cruise', 'watercraft', 'sail', 'canvas', '=raft']
        } else if (word == BICYCLE) {
            word = ['bicycle', 'tricycle', 'mountain bike', 'AcceleratorPedal', 'macaw', 'knot']
        } else if (word == MOTORCYCLE) {
            word = ['motorcycle', 'windshield', 'dashboard']
        } else if (word == TRUCK) {
            word = ['truck', 'cargocontainer', 'bazooka']
        } else {
            console.log("Word does not match. New type identified::" + word);
        }

        return word

    }

    function isHidden(el) {
        return (el.offsetParent === null)
    }

    if (window.location.href.includes("checkbox")) {
        var checkboxInterval = setInterval(function() {
            if (!qSelector(CHECK_BOX)) {
                clearInterval(checkboxInterval);
            } else if (qSelector(CHECK_BOX).getAttribute(ARIA_CHECKED) == "true") {
                clearInterval(checkboxInterval);
            } else if (!isHidden(qSelector(CHECK_BOX)) && qSelector(CHECK_BOX).getAttribute(ARIA_CHECKED) == "false") {
                qSelector(CHECK_BOX).click();
            } else {
                return;
            }

        }, 5000);
    } else {

        try {
            initializeTesseractWorker();
            selectImages();

        } catch (err) {
            console.log(err);
            console.log("Tesseract could not be initialized");
        }

    }

    function selectImagesAfterDelay(delay) {
        setTimeout(function() {
            selectImages();
        }, delay * 1000);
    }

    function triggerEvent(el, type) {
        var e = document.createEvent('HTMLEvents');
        e.initEvent(type, false, true);
        el.dispatchEvent(e);
    }

    // Small hack to select the nodes
    function unsure(targetNodeText) {
        var targetNode = Array.from(qSelectorAll('div'))
        .find(el => el.textContent === targetNodeText);
        //Works for now
        //TODO: Select clothing
        //TODO: Draw boxes around images
        if (targetNode) {
            triggerEvent(targetNode, 'mousedown');
            triggerEvent(targetNode, 'mouseup');
            if (qSelector(SUBMIT_BUTTON)) {
                qSelector(SUBMIT_BUTTON).click();
            }
        }
        return selectImagesAfterDelay(1);
    }

    function getUrlFromString(urlString) {
        var urlMatch = urlString.match(/(?<=\(\").+?(?=\"\))/g);
        if (!urlMatch) {
            return 0;
        }
        var imageUrl = urlMatch[0];
        return imageUrl;
    }


    function getImageList() {
        var imageList = [];
        if (qSelectorAll(IMAGE).length > 0) {
            for (var i = 0; i < 9; i++) {
                var urlString = qSelectorAll(IMAGE)[i].style.background;
                var imageUrl = getUrlFromString(urlString);
                if (imageUrl == 0) {
                    //console.log("Image url is empty");
                    return imageList;
                }
                imageList[i] = imageUrl;
            }
        }
        return imageList;
    }

    function waitUntilImageSelection() {
        var imageIntervalCount = 0;
        var imageInterval = setInterval(function() {
            imageIntervalCount = imageIntervalCount + 1;
            if (selectedImageCount == 9) {
                clearInterval(imageInterval);
                if (qSelector(SUBMIT_BUTTON)) {
                    qSelector(SUBMIT_BUTTON).click();
                }
                return selectImagesAfterDelay(5);
            } else if (imageIntervalCount > 8) {
                clearInterval(imageInterval);
                return selectImages();
            } else {

            }
        }, 3000);
    }

    function waitForImagesToAppear() {
        var checkImagesSelectedCount = 0;
        var waitForImagesInterval = setInterval(function() {
            checkImagesSelectedCount = checkImagesSelectedCount + 1;
            if (qSelectorAll(IMAGE) && qSelectorAll(IMAGE).length == 9) {
                clearInterval(waitForImagesInterval);
                return selectImages();
            } else if (checkImagesSelectedCount > 30) {
                clearInterval(waitForImagesInterval);
            } else if (qSelector(CHALLENGE_INPUT_FIELD) && qSelector(NO_SELECTION).getAttribute(ARIA_HIDDEN) != true) {
                clearInterval(waitForImagesInterval);
                return imageUsingOCR();
            } else {
                //TODO: Identify Objects for the following (Ex: bed,chair,table etc)
                //Ref for clothing: https://www.youtube.com/watch?v=yWwzFnAnrLM, https://www.youtube.com/watch?v=FiNglI1wRNk,https://www.youtube.com/watch?v=oHAkK_9UCQ8
                var targetNodeList = ["3 or more items of furniture", "Equipped space or room", "Photo is clean, no watermarks, logos or text overlays", "An interior photo of room", "Unsure", "Photo is sharp"];
                for (var j = 0; j < targetNodeList.length; j++) {
                    var targetNode = Array.from(qSelectorAll('div'))
                    .find(el => el.textContent === targetNodeList[j]);
                    if (targetNode) {
                        //console.log("Target Node Found");
                        clearInterval(waitForImagesInterval);
                        return unsure(targetNodeList[j]);
                    }
                }
            }
        }, 5000);
    }

    function preProcessImage(imageUrl) {

        //Darken and Brighten
        Jimp.read(imageUrl).then(function(data) {
            data.color([

                {
                    apply: 'darken',
                    params: [20]
                }

            ]).color([

                {
                    apply: 'brighten',
                    params: [20]
                }

            ])
                .greyscale()
                .getBase64(Jimp.AUTO, function(err, src) {
                var img = document.createElement("img");
                img.setAttribute("src", src);

                worker.recognize(img, LANGUAGE_FOR_OCR).then(function(data) {
                    //Remove Image After recognizing
                    img.removeAttribute("src");
                    //If null change to other methods
                    if (data && data.text && data.text.length > 0) {
                        inputChallenge(postProcessImage(data), imageUrl);
                        return selectImages();
                    } else {
                        preProcessImageMethod2(imageUrl);
                    }
                });

            });
        });

    }


    function preProcessImageMethod2(imageUrl) {

        //Multi Contrast darken and brighten
        Jimp.read(imageUrl).then(function(data) {
            data.color([

                {
                    apply: 'darken',
                    params: [20]
                }

            ]).contrast(1).color([

                {
                    apply: 'brighten',
                    params: [20]
                }

            ]).contrast(1).greyscale().getBase64(Jimp.AUTO, function(err, src) {
                var img = document.createElement("img");
                img.setAttribute("src", src);

                worker.recognize(img, LANGUAGE_FOR_OCR).then(function(data) {
                    //Remove Image After recognizing
                    img.removeAttribute("src");
                    if (data && data.text && data.text.length > 0) {
                        inputChallenge(postProcessImage(data), imageUrl);
                        return selectImages();
                    } else {
                        preProcessImageMethod3(imageUrl);
                    }
                });
            });
        });

    }

    function preProcessImageMethod3(imageUrl) {
        //Multi Contrast only brighten
        Jimp.read(imageUrl).then(function(data) {
            data.contrast(1).color([{
                apply: 'brighten',
                params: [20]
            }

                                   ])
                .contrast(1)
                .greyscale()
                .getBase64(Jimp.AUTO, function(err, src) {
                var img = document.createElement("img");
                img.setAttribute("src", src);

                worker.recognize(img, LANGUAGE_FOR_OCR).then(function(data) {
                    //Remove Image After recognizing
                    img.removeAttribute("src");
                    if (data && data.text && data.text.length > 0) {
                        inputChallenge(postProcessImage(data), imageUrl);
                        return selectImages();
                    } else {
                        preProcessImageMethod4(imageUrl);
                    }
                });
            });
        });
    }

    function preProcessImageMethod4(imageUrl) {
        //Resize the image
        Jimp.read(imageUrl).then(function(data) {
            data.resize(256, Jimp.AUTO)
                .quality(60) // set JPEG quality
                .greyscale() // set greyscale
                .getBase64(Jimp.AUTO, function(err, src) {
                var img = document.createElement("img");
                img.setAttribute("src", src);

                worker.recognize(img, LANGUAGE_FOR_OCR).then(function(data) {
                    //Remove Image After recognizing
                    img.removeAttribute("src");
                    inputChallenge(postProcessImage(data), imageUrl);
                    return selectImages();
                });
            });
        });

    }

    function postProcessImage(data) {
        var filterValues = ['\n', '{', '}', '[', ']'];
        for (var i = 0; i < filterValues.length; i++) {
            data.text = data.text.replaceAll(filterValues[i], "");
        }
        return data;
    }

    // Using Tesseract to recognize images
    function imageUsingOCR() {
        try {
            //console.log("Image using OCR");
            var urlString = qSelector(IMAGE_FOR_OCR).style.background;
            var imageUrl = getUrlFromString(urlString);
            if (imageUrl == 0) {
                return selectImagesAfterDelay(1);
            }

            preProcessImage(imageUrl);

        } catch (err) {
            console.log(err.message);
            return selectImagesAfterDelay(1);
        }
    }


    async function convertTextToImage(text) {

        //Convert Text to image
        var canvas = document.createElement("canvas");
        canvas.width = 620;
        canvas.height = 80;
        var ctx = canvas.getContext('2d');
        ctx.font = "30px Arial";
        ctx.fillText(text, 10, 50);
        var img = document.createElement("img");
        img.src = canvas.toDataURL();

        return img;
    }

    async function convertImageToText(img) {

        //Convert Image to Text
        var text = "";
        await worker.recognize(img, LANGUAGE_FOR_OCR).then(function(data) {
            text = data.text;
            // console.log("Recognized Text::" + text);
        });
        return text.trim();
    }

    function inputChallenge(data, imageUrl) {
        try {
            if ((qSelector(IMAGE_FOR_OCR).style.background).includes(imageUrl)) {
                console.log(data.text);
                var targetNode = qSelector(CHALLENGE_INPUT_FIELD);
                targetNode.value = data.text.replaceAll("\n", "");
                var challengeInput = qSelector(CHALLENGE_INPUT);
                triggerEvent(challengeInput, 'input');
                // Set a timeout if you want to see the text
                qSelector(SUBMIT_BUTTON).click();
            }

        } catch (err) {
            console.log(err.message);
        }
    }


    async function selectImages() {

        if (qSelectorAll(IMAGE) && qSelectorAll(IMAGE).length == 9 && qSelector(NO_SELECTION).getAttribute(ARIA_HIDDEN) != true) {
            selectedImageCount = 0;
            try {
                await initializeTensorFlowModel();

                var word = qSelector(PROMPT_TEXT).innerText;
                if (word && (word.includes(SENTENCE_TEXT_A) || word.includes(SENTENCE_TEXT_AN))) {
                    word = word.replace(SENTENCE_TEXT_A, '');
                    word = word.replace(SENTENCE_TEXT_AN, '');
                } else {
                    //TODO: Select images from example and identify the word for other languages
                }
            } catch (err) {
                console.log(err.message);
                return selectImagesAfterDelay(5);
            }

            var imageList = [];
            try {
                imageList = getImageList();
                if (imageList.length != 9) {
                    //console.log("Waiting");
                    return selectImagesAfterDelay(5);
                }
            } catch (err) {
                console.log(err.message);
                return selectImagesAfterDelay(5);
            }
            //Get Synonyms for the word
            word = await getSynonyms(word);
            //console.log("words are::" + word);

            for (var i = 0; i < 9; i++) {
                if (ENABLE_TENSORFLOW) {
                    matchImagesUsingTensorFlow(imageList[i], word, i);
                } else {
                    matchImages(imageList[i], word, i);
                }
            }
            waitUntilImageSelection();

        } else {
            waitForImagesToAppear();
        }
    }


})();
```>)
