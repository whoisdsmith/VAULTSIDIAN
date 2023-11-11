# Chrome Flags

---

Reset all

# Experiments

107.0.5304.121

WARNING: EXPERIMENTAL FEATURES AHEAD! By enabling these features, you could lose browser data or compromise your security or privacy. Enabled features apply to all users of this browser. If you are an enterprise admin you should not be using these flags in production.

Interested in cool new Chrome features? Try our [beta channel](https://chrome.com/beta).

- [Available](chrome://flags/#tab-content-available)
- [Unavailable](chrome://flags/#tab-content-unavailable)

## Temporarily Unexpire M105 Flags

Temporarily unexpire flags that expired as of M105. These flags will be removed soon. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#temporary-unexpire-flags-m105](chrome://flags/#temporary-unexpire-flags-m105)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Temporarily Unexpire M106 Flags

Temporarily unexpire flags that expired as of M106. These flags will be removed soon. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#temporary-unexpire-flags-m106](chrome://flags/#temporary-unexpire-flags-m106)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Override Software Rendering List

Overrides the built-in software rendering list and enables GPU-acceleration on unsupported system configurations. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#ignore-gpu-blocklist](chrome://flags/#ignore-gpu-blocklist)

                 Disabled                 Enabled

## Accelerated 2D Canvas

Enables the use of the GPU to perform 2d canvas rendering instead of using software rendering. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#disable-accelerated-2d-canvas](chrome://flags/#disable-accelerated-2d-canvas)

                 Disabled                 Enabled

## Select HW Overlay Strategies

Select strategies used to promote quads to HW overlays. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#overlay-strategies](chrome://flags/#overlay-strategies)

                   DefaultNoneUnoccluded fullscreen buffers (single-fullscreen)Unoccluded buffers (single-fullscreen,single-on-top)Occluded and unoccluded buffers (single-fullscreen,single-on-top,underlay)

                 Disabled                 Enabled

## Tint Composited Content

Tint contents composited using Viz with a shade of red to help debug and study overlay support. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#tint-composited-content](chrome://flags/#tint-composited-content)

                 Disabled                 Enabled

## Show Overdraw Feedback

Visualize overdraw by color-coding elements based on if they have other elements drawn underneath. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#show-overdraw-feedback](chrome://flags/#show-overdraw-feedback)

                 Disabled                 Enabled

## Partial Swap

Sets partial swap behavior. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#ui-disable-partial-swap](chrome://flags/#ui-disable-partial-swap)

                 Disabled                 Enabled

## Enable Reader Mode

Allows viewing of simplified web pages by selecting 'Customize and control Chrome'>'Distill page' – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-reader-mode](chrome://flags/#enable-reader-mode)

                   DefaultEnabledEnabled available in settingsDisabled

                 Disabled                 Enabled

## Anonymize Local IPs Exposed by WebRTC

Conceal local IP addresses with mDNS hostnames. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-webrtc-hide-local-ips-with-mdns](chrome://flags/#enable-webrtc-hide-local-ips-with-mdns)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Extensions on chrome:// URLs

Enables running extensions on chrome:// URLs, where extensions explicitly request this permission. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#extensions-on-chrome-urls](chrome://flags/#extensions-on-chrome-urls)

                 Disabled                 Enabled

## Show Autofill Predictions

Annotates web forms with Autofill field type predictions as placeholder text. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#show-autofill-type-predictions](chrome://flags/#show-autofill-type-predictions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental QUIC Protocol

Enable experimental QUIC protocol support. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-quic](chrome://flags/#enable-quic)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Latest Stable JavaScript Features

Some web pages use legacy or non-standard JavaScript extensions that may conflict with the latest JavaScript features. This flag allows disabling support of those features for compatibility with such pages. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#disable-javascript-harmony-shipping](chrome://flags/#disable-javascript-harmony-shipping)

                 Disabled                 Enabled

## Experimental JavaScript

Enable web pages to use experimental JavaScript features. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-javascript-harmony](chrome://flags/#enable-javascript-harmony)

                 Disabled                 Enabled

## Experimental JavaScript Shared Memory Features

Enable web pages to use non-standard, experimental JavaScript shared memory features. Their use requires the same HTTP headers required by cross-thread usage of SharedArrayBuffers (i.e. COOP and COEP). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-javascript-experimental-shared-memory](chrome://flags/#enable-javascript-experimental-shared-memory)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental WebAssembly

Enable web pages to use experimental WebAssembly features. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-experimental-webassembly-features](chrome://flags/#enable-experimental-webassembly-features)

                 Disabled                 Enabled

## WebAssembly Baseline Compiler

Enables WebAssembly baseline compilation and tier up. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-webassembly-baseline](chrome://flags/#enable-webassembly-baseline)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## WebAssembly Lazy Compilation

Enables lazy (JIT on first call) compilation of WebAssembly modules. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-webassembly-lazy-compilation](chrome://flags/#enable-webassembly-lazy-compilation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## WebAssembly Tiering

Enables tiered compilation of WebAssembly (will tier up to TurboFan if #enable-webassembly-baseline is enabled). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-webassembly-tiering](chrome://flags/#enable-webassembly-tiering)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Future V8 VM Features

This enables upcoming and experimental V8 VM features. This flag does not enable experimental JavaScript features. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-future-v8-vm-features](chrome://flags/#enable-future-v8-vm-features)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## GPU Rasterization

Use GPU to rasterize web content. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-gpu-rasterization](chrome://flags/#enable-gpu-rasterization)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental Web Platform Features

Enables experimental Web Platform features that are in development. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-experimental-web-platform-features](chrome://flags/#enable-experimental-web-platform-features)

                 Disabled                 Enabled

## Touch UI Layout

Enables touch UI layout in the browser's top chrome. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#top-chrome-touch-ui](chrome://flags/#top-chrome-touch-ui)

                   DefaultAutomaticDisabledEnabled

                 Disabled                 Enabled

## Variable COLRv1 Fonts

Enable rendering of COLRv1 glyphs with font variations applied. When this flag is off, variations to COLRv1 tables are ignored. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#variable-colrv1](chrome://flags/#variable-colrv1)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Hardware-accelerated Video Decode

Hardware-accelerated video decode where available. – Mac, Windows, ChromeOS, Android, Fuchsia, Lacros

[#disable-accelerated-video-decode](chrome://flags/#disable-accelerated-video-decode)

                 Disabled                 Enabled

## Hardware-accelerated Video Encode

Hardware-accelerated video encode where available. – Mac, Windows, ChromeOS, Android

[#disable-accelerated-video-encode](chrome://flags/#disable-accelerated-video-encode)

                 Disabled                 Enabled

## Debugging for Packed Apps

Enables debugging context menu options such as Inspect Element for packed applications. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#debug-packed-apps](chrome://flags/#debug-packed-apps)

                 Disabled                 Enabled

## Username First Flow Fallback Crowdsourcing

Support of sending additional votes on username first flow i.e. login flows where a user has to type username first on one page and then password on another page. These votes are sent on single password forms and contain information whether a 1-password form follows a 1-text form and the value's type(or pattern) in the latter (e.g. email-like, phone-like, arbitrary string). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#username-first-flow-fallback-crowdsourcing](chrome://flags/#username-first-flow-fallback-crowdsourcing)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Show Autofill Signatures

Annotates web forms with Autofill signatures as HTML attributes. Also marks password fields suitable for password generation. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-show-autofill-signatures](chrome://flags/#enable-show-autofill-signatures)

                 Disabled                 Enabled

## Use Google Payments Sandbox Servers

For developers: use the sandbox service for Google Payments API calls. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#wallet-service-use-sandbox](chrome://flags/#wallet-service-use-sandbox)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use the New Permissions Backend for Web Bluetooth

Enables the new permissions backend for Web Bluetooth. This will enable persistent storage of device permissions and Web Bluetooth features such as BluetoothDevice.watchAdvertisements() and Bluetooth.getDevices() – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-web-bluetooth-new-permissions-backend](chrome://flags/#enable-web-bluetooth-new-permissions-backend)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Automatic Detection of WebUSB-compatible Devices

When enabled, the user will be notified when a device which advertises support for WebUSB is connected. Disable if problems with USB devices are observed when the browser is running. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-webusb-device-detection](chrome://flags/#enable-webusb-device-detection)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## WebGL Developer Extensions

Enabling this option allows web applications to access WebGL extensions intended only for use during development time. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-webgl-developer-extensions](chrome://flags/#enable-webgl-developer-extensions)

                 Disabled                 Enabled

## WebGL Draft Extensions

Enabling this option allows web applications to access the WebGL extensions that are still in draft status. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-webgl-draft-extensions](chrome://flags/#enable-webgl-draft-extensions)

                 Disabled                 Enabled

## Zero-copy Rasterizer

Raster threads write directly to GPU memory associated with tiles. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-zero-copy](chrome://flags/#enable-zero-copy)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable System Notifications

Enable support for using the system notification toasts and notification center on platforms where these are available. – Mac, Windows, Linux

[#enable-system-notifications](chrome://flags/#enable-system-notifications)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## In-Product Help Demo Mode

Selects the In-Product Help demo mode. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#in-product-help-demo-mode-choice](chrome://flags/#in-product-help-demo-mode-choice)

                   DefaultEnabledEnabled IPH_BatterySaverModeEnabled IPH_DesktopTabGroupsNewGroupEnabled IPH_ExtensionsMenuEnabled IPH_FocusModeEnabled IPH_GlobalMediaControlsEnabled IPH_GMCCastStartStopEnabled IPH_LiveCaptionEnabled IPH_PasswordsAccountStorageEnabled IPH_ReadingListDiscoveryEnabled IPH_ReadingListEntryPointEnabled IPH_ReadingListInSidePanelEnabled IPH_ReopenTabEnabled IPH_SideSearchAutoTriggeringEnabled IPH_SideSearchEnabled IPH_SideSearchPageActionLabelEnabled IPH_TabAudioMutingEnabled IPH_TabSearchEnabled IPH_WebUITabStripEnabled IPH_DesktopPwaInstallEnabled IPH_ProfileSwitchEnabled IPH_DesktopSharedHighlightingEnabled IPH_IntentChipEnabled IPH_WebUiHelpBubbleTestEnabled IPH_AutofillVirtualCardSuggestionDisabled

                 Disabled                 Enabled

## IPH Use Client Config

Enable In-Product Help to use client side configuration. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#in-product-help-use-client-config](chrome://flags/#in-product-help-use-client-config)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Threaded Scrolling

Threaded handling of scroll-related input events. Disabling this will force all such scroll events to be handled on the main thread. Note that this can dramatically hurt scrolling performance of most websites and is intended for testing purposes only. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#disable-threaded-scrolling](chrome://flags/#disable-threaded-scrolling)

                 Disabled                 Enabled

## Enable Isolated Web Apps

Enables experimental support for isolated web apps. See <https://github.com/reillyeon/isolated-web-apps> for more information. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-isolated-web-apps](chrome://flags/#enable-isolated-web-apps)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Install Isolated Apps at Startup

Isolated application URLs that Chrome should install during startup, specified as a comma-separated list – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#install-isolated-apps-at-startup](chrome://flags/#install-isolated-apps-at-startup)

                 Disabled                 Enabled

## Isolate Additional Origins

Requires dedicated processes for an additional set of origins, specified as a comma-separated list. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#isolate-origins](chrome://flags/#isolate-origins)

                 Disabled                 Enabled

## Isolated App Origins

Enables Isolated App policy enforcement and related APIs (e.g. Direct Sockets API) for development purposes for a set of origins, specified as a comma-separated list. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#isolated-app-origins](chrome://flags/#isolated-app-origins)

                 Disabled                 Enabled

## Disable Site Isolation

Disables site isolation (SitePerProcess, IsolateOrigins, etc). Intended for diagnosing bugs that may be due to out-of-process iframes. Opt-out has no effect if site isolation is force-enabled using a command line switch or using an enterprise policy. Caution: this disables important mitigations for the Spectre CPU vulnerability affecting most computers. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#site-isolation-trial-opt-out](chrome://flags/#site-isolation-trial-opt-out)

                   DefaultDisabled (not recommended)

                 Disabled                 Enabled

## Site Isolation for Webview Tags

Enables site isolation for content rendered inside `<webview>` tags. This increases security for Chrome Apps and WebUI pages that use `<webview>`. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

---

[#enable-webview-tag-site-isolation](chrome://flags/#enable-webview-tag-site-isolation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Invalid Certificates for Resources Loaded From Localhost

Allows requests to localhost over HTTPS even when an invalid certificate is presented. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#allow-insecure-localhost](chrome://flags/#allow-insecure-localhost)

                 Disabled                 Enabled

## Enable Audio Descriptions

When enabled, HTML5 video elements with a 'descriptions' WebVTT track will speak the audio descriptions aloud as the video plays. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#text-based-audio-descriptions](chrome://flags/#text-based-audio-descriptions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Bypass User Engagement Checks

Bypasses user engagement checks for displaying app banners, such as requiring that users have visited the site before and that the banner hasn't been shown recently. This allows developers to test that other eligibility requirements for showing app banners, such as having a manifest, are met. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#bypass-app-banner-engagement-checks](chrome://flags/#bypass-app-banner-engagement-checks)

                 Disabled                 Enabled

## Desktop PWAs Remove Status Bar

Hides the status bar popup in Desktop PWA app windows. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-remove-status-bar](chrome://flags/#enable-desktop-pwas-remove-status-bar)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Default Offline Page for PWAs

Shows customised default offline page when web app is offline. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-pwas-default-offline-page](chrome://flags/#enable-pwas-default-offline-page)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWA Tab Strips

Experimental UI for exploring what PWA windows would look like with a tab strip. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-tab-strip](chrome://flags/#enable-desktop-pwas-tab-strip)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWA Tab Strips Settings

Experimental UI for selecting whether a PWA should open in tabbed mode. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-tab-strip-settings](chrome://flags/#enable-desktop-pwas-tab-strip-settings)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWA Launch Handler

Enable web app manifests to declare app launch behavior. Prototype implementation of: <https://github.com/WICG/sw-launch/blob/main/launch_handler.md> – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-launch-handler](chrome://flags/#enable-desktop-pwas-launch-handler)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWA Sub Apps

Enable installed PWAs to create shortcuts by installing their sub apps. Prototype implementation of: <https://github.com/ivansandrk/multi-apps/blob/main/explainer.md> – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-sub-apps](chrome://flags/#enable-desktop-pwas-sub-apps)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWA Window Minimize/maximize/restore

Enable PWAs to manually recreate the minimize, maximize and restore window functionalities with respective APIs. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-additional-windowing-controls](chrome://flags/#enable-desktop-pwas-additional-windowing-controls)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWAs Web Bundles

Adds support for web bundles, making web apps able to be launched offline. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-web-bundles](chrome://flags/#enable-desktop-pwas-web-bundles)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWAs Detailed Install Dialog

Enable PWAs with screenshots to show a detailed install dialog during installation – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-desktop-pwas-detailed-install-dialog](chrome://flags/#enable-desktop-pwas-detailed-install-dialog)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Record Web App Debug Info

Enables recording additional web app related debugging data to be displayed in: chrome://web-app-internals – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#record-web-app-debug-info](chrome://flags/#record-web-app-debug-info)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use Chrome Sync Sandbox

Connects to the testing server for Chrome Sync. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#use-sync-sandbox](chrome://flags/#use-sync-sandbox)

                 Disabled                 Enabled

## Block Migrated Default Chrome App Sync

Prevents Chrome apps that have been migrated to default web apps from getting sync installed and creating duplicate entries for the same app. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#block-migrated-default-chrome-app-sync](chrome://flags/#block-migrated-default-chrome-app-sync)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Connect to Cast Devices on All IP Addresses

Have the Media Router connect to Cast devices on all IP addresses, not just RFC1918/RFC4193 private addresses. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#media-router-cast-allow-all-ips](chrome://flags/#media-router-cast-allow-all-ips)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Global Media Controls Control Cast start/stop

Allows global media controls to control when a Cast session is started or stopped instead of relying on the Cast dialog. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#global-media-controls-cast-start-stop](chrome://flags/#global-media-controls-cast-start-stop)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow All Sites to Initiate Mirroring

When enabled, allows all websites to request to initiate tab mirroring via Presentation API. Requires #cast-media-route-provider to also be enabled – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#allow-all-sites-to-initiate-mirroring](chrome://flags/#allow-all-sites-to-initiate-mirroring)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Migrate Default G Suite Chrome Apps to Web Apps

Enable the migration of default installed G Suite Chrome apps over to their corresponding web apps. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-migrate-default-chrome-app-to-web-apps-gsuite](chrome://flags/#enable-migrate-default-chrome-app-to-web-apps-gsuite)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Migrate Default non-G Suite Chrome Apps to Web Apps

Enable the migration of default installed non-G Suite Chrome apps over to their corresponding web apps. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-migrate-default-chrome-app-to-web-apps-non-gsuite](chrome://flags/#enable-migrate-default-chrome-app-to-web-apps-non-gsuite)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable the App Deduplication Fix for Migrated Preinstalled Web Apps

The preinstalled web app migration encountered app duplication issues when it rolled out. This code path will attempt to re-migrate instances of app duplication where the old app failed to stay removed. See <https://crbug.com/1290716>. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-preinstalled-web-app-duplication-fixer](chrome://flags/#enable-preinstalled-web-app-duplication-fixer)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Open Screen Library (libcast) as the Mirroring Service's Cast Streaming Implementation

Enables Open Screen Library's (libcast) Cast Streaming implementation to be used for negotiating and executing mirroring and remoting sessions. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-openscreen-cast-streaming-session](chrome://flags/#enable-openscreen-cast-streaming-session)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable AV1 Codec Video Encoding in Cast Mirroring Sessions

Enables the inclusion of AV1 codec video encoding in Cast mirroring session negotiations. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-cast-streaming-av1](chrome://flags/#enable-cast-streaming-av1)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable VP9 Codec Video Encoding in Cast Mirroring Sessions

Enables the inclusion of VP9 codec video encoding in Cast mirroring session negotiations. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-cast-streaming-vp9](chrome://flags/#enable-cast-streaming-vp9)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use Blocklist for Controlling Remoting Capabilities Queries

Enables the use of the hard-coded blocklist for controlling whether a device should be queried for remoting capabilities when configuring a mirroring session. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-cast-remoting-query-blocklist](chrome://flags/#enable-cast-remoting-query-blocklist)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Force Enable Remoting Capabilities Queries

Enables querying for remoting capabilities for ALL devices, regardless of the contents of the allowlist or blocklist. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#force-enable-cast-remoting-query](chrome://flags/#force-enable-cast-remoting-query)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Web Share

Enables the Web Share (navigator.share) APIs on experimentally supported platforms. – Mac, Windows, ChromeOS

[#web-share](chrome://flags/#web-share)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental System Keyboard Lock

Enables websites to use the keyboard.lock() API to intercept system keyboard shortcuts and have the events routed directly to the website when in fullscreen mode. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#system-keyboard-lock](chrome://flags/#system-keyboard-lock)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Block Scripts Loaded via document.write

Disallows fetches for third-party parser-blocking scripts inserted into the main frame via document.write. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#disallow-doc-written-script-loads](chrome://flags/#disallow-doc-written-script-loads)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## documentTransition API

Controls the availability of the documentTransition JavaScript API. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#document-transition](chrome://flags/#document-transition)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Offering Upload of Autofilled Credit Cards

Enables a new option to upload credit cards to Google Payments for sync to all Chrome devices. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-autofill-credit-card-upload](chrome://flags/#enable-autofill-credit-card-upload)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Force UI Direction

Explicitly force the UI to left-to-right (LTR) or right-to-left (RTL) mode, overriding the default direction of the UI language. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-ui-direction](chrome://flags/#force-ui-direction)

                   DefaultLeft-to-rightRight-to-left

                 Disabled                 Enabled

## Force Text Direction

Explicitly force the per-character directionality of UI text to left-to-right (LTR) or right-to-left (RTL) mode, overriding the default direction of the character language. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-text-direction](chrome://flags/#force-text-direction)

                   DefaultLeft-to-rightRight-to-left

                 Disabled                 Enabled

## Following Feed in the Sidepanel

Enables the following feed in the sidepanel. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#following-feed-sidepanel](chrome://flags/#following-feed-sidepanel)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Password Import

Import functionality in password settings. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#password-import](chrome://flags/#password-import)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Auto Dark Mode for Web Contents

Automatically render all web contents using a dark theme. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-force-dark](chrome://flags/#enable-force-dark)

                   DefaultEnabledEnabled with simple HSL-based inversionEnabled with simple CIELAB-based inversionEnabled with simple RGB-based inversionEnabled with selective image inversionEnabled with selective inversion of non-image elementsEnabled with selective inversion of everythingDisabled

                 Disabled                 Enabled

## Immersive Fullscreen Toolbar

Automatically hide and show the toolbar in fullscreen. – Mac

[#enable-immersive-fullscreen-toolbar](chrome://flags/#enable-immersive-fullscreen-toolbar)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental Web Payments API Features

Enable experimental Web Payments API features – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-web-payments-experimental-features](chrome://flags/#enable-web-payments-experimental-features)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## CSP Policy for Web Payment API

Enforce Content Security Policy connect-src directive for Web Payment API when fetching manifest files, app icons, and service worker JavaScript files. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#web-payment-api-csp](chrome://flags/#web-payment-api-csp)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Identity in Canmakepayment Event

The payment app receives the merchant and user identity when the merchant checks whether this payment app is present and can make payments. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#identity-in-can-make-payment](chrome://flags/#identity-in-can-make-payment)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Web Payments App Store Billing Debug Mode

App-store purchases (e.g., Google Play Store) within a TWA can be requested using the Payment Request API. This flag removes the restriction that the TWA has to be installed from the app-store. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-debug-for-store-billing](chrome://flags/#enable-debug-for-store-billing)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Secure Payment Confirmation Debug Mode

This flag removes the restriction that PaymentCredential in WebAuthn and secure payment confirmation in PaymentRequest API must use user verifying platform authenticators. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-debug-for-secure-payment-confirmation](chrome://flags/#enable-debug-for-secure-payment-confirmation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Fill Passwords on Account Selection

Filling of passwords when an account is explicitly selected by the user rather than autofilling credentials on page load. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#fill-on-account-select](chrome://flags/#fill-on-account-select)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Generic Sensor Extra Classes

Enables an extra set of sensor classes based on Generic Sensor API, which expose previously unavailable platform features, i.e. AmbientLightSensor and Magnetometer interfaces. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-generic-sensor-extra-classes](chrome://flags/#enable-generic-sensor-extra-classes)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Universal Links

Include Universal Links in the intent picker. – Mac

[#enable-universal-links](chrome://flags/#enable-universal-links)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Local History Zero-prefix Suggestions Beyond NTP

Enables local history zero-prefix suggestions in every context in which the remote zero-prefix suggestions are enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-local-history-zero-suggest-beyond-ntp](chrome://flags/#omnibox-local-history-zero-suggest-beyond-ntp)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox On-focus Suggestions for the Contextual Web

Enables on-focus suggestions on the Open Web, that are contextual to the current URL. Will only work if user is signed-in and syncing, or is otherwise eligible to send the current page URL to the suggest server. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-on-focus-suggestions-contextual-web](chrome://flags/#omnibox-on-focus-suggestions-contextual-web)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Omnibox Contextual Web On-focus Suggestions on the SRP

Enables on-focus suggestions on the Search Results page. Requires on-focus suggestions for the contextual web to be enabled. Will only work if user is signed-in and syncing. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-on-focus-suggestions-srp](chrome://flags/#omnibox-on-focus-suggestions-srp)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Fuzzy URL Suggestions

Enables URL suggestions for inputs that may contain typos. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-fuzzy-url-suggestions](chrome://flags/#omnibox-fuzzy-url-suggestions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Zero Prefix Suggestion Prefetching on NTP

Enables prefetching of the zero prefix suggestions for eligible users on the New Tab page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-zero-suggest-prefetching](chrome://flags/#omnibox-zero-suggest-prefetching)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Zero Prefix Suggestion Prefetching on SRP

Enables prefetching of the zero prefix suggestions for eligible users on the Search Results page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-zero-suggest-prefetching-on-srp](chrome://flags/#omnibox-zero-suggest-prefetching-on-srp)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Zero Prefix Suggestion Prefetching on the Web

Enables prefetching of the zero prefix suggestions for eligible users on the Web (i.e. non-NTP and non-SRP URLs). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-zero-suggest-prefetching-on-web](chrome://flags/#omnibox-zero-suggest-prefetching-on-web)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Zero Prefix Suggestion In-memory Caching

Enables in-memory caching of zero prefix suggestions. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-zero-suggest-in-memory-caching](chrome://flags/#omnibox-zero-suggest-in-memory-caching)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Rich Autocompletion Promising Combinations

Allow autocompletion for titles and non-prefixes. Suggestions whose titles or URLs contain the user input as a continuous chunk, but not necessarily a prefix, can be the default suggestion. Otherwise, only suggestions whose URLs are prefixed by the user input can be. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-rich-autocompletion-promising](chrome://flags/#omnibox-rich-autocompletion-promising)

                   DefaultEnabledEnabled Conservative Moderate - Title, Shortcut Non-Prefix, min 3/5Enabled Conservative Moderate 2 - Shortcut Title, Shortcut Non-Prefix, min 3/5Enabled Aggressive 2 - Title Shortcut Title 2, Shortcut Text 2Enabled Aggressive 3 - Title Shortcut Title 3, Shortcut Text 3Enabled Aggressive 4 - Title Shortcut Title 4, Shortcut Text 4Disabled

                 Disabled                 Enabled

## Omnibox Document Provider ASO

If document suggestions are enabled, swaps the backend from cloudsearch to ASO (Apps Search Overlay) search. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-document-provider-aso](chrome://flags/#omnibox-document-provider-aso)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Site Search Starter Pack

Enables @history, @bookmarks, and @tabs scopes in Omnibox Site Search/Keyword Mode – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-site-search-starter-pack](chrome://flags/#omnibox-site-search-starter-pack)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Shortcut Expanding

Expand the last word in the shortcut text to be a complete word from the suggestion text. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-shortcut-expanding](chrome://flags/#omnibox-shortcut-expanding)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Close Popup with Escape

When enabled, pressing escape when the omnibox popup is open and the default suggestion is selected will close the omnibox without removing its focus or clearing user input. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-close-popup-with-escape](chrome://flags/#omnibox-close-popup-with-escape)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Blur with Escape

When enabled, pressing escape when the omnibox is focused without user input will blur the omnibox and focus the web page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#omnibox-blur-with-escape](chrome://flags/#omnibox-blur-with-escape)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Force Color Profile

Forces Chrome to use a specific color profile instead of the color of the window's current monitor, as specified by the operating system. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-color-profile](chrome://flags/#force-color-profile)

                   DefaultsRGBDisplay P3 D65Color spin with gamma 2.4scRGB linear (HDR where available)HDR10 (HDR where available)

                 Disabled                 Enabled

## Forced Colors

Enables forced colors mode for web content. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#forced-colors](chrome://flags/#forced-colors)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Chrome Heap Profiler Start Mode

Starts heap profiling service that records sampled memory allocation profile having each sample attributed with a callstack. The sampling resolution is controlled with --memlog-sampling-rate flag. Recorded heap dumps can be obtained at chrome://tracing [category:memory-infra] and chrome://memory-internals. This setting controls which processes will be profiled since their start. To profile any given process at a later time use chrome://memory-internals page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#memlog](chrome://flags/#memlog)

                   DisabledBrowser and GPUAll processesBrowser onlyGPU onlyAll renderersSingle renderer

                 Disabled                 Enabled

## Heap Profiling Sampling Interval (in bytes)

Heap profiling service uses Poisson process to sample allocations. Default value for the interval between samples is 1000000 (1MB). This results in low noise for large and/or frequent allocations [size * frequency >> 1MB]. This means that aggregate numbers [e.g. total size of malloc-ed objects] and large and/or frequent allocations can be trusted with high fidelity. Lower intervals produce higher samples resolution, but come at a cost of higher performance overhead. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#memlog-sampling-rate](chrome://flags/#memlog-sampling-rate)

                   Default10KB50KB100KB500KB1MB5MB

                 Disabled                 Enabled

## Heap Profiling Stack Traces Type

By default heap profiling service records native stacks. A post-processing step is required to symbolize the stacks. 'Native with thread names' adds the thread name as the first frame of each native stack. It's also possible to record a pseudo stack using trace events as identifiers. It's also possible to do a mix of both. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#memlog-stack-mode](chrome://flags/#memlog-stack-mode)

                   DefaultNativeNative with thread names

                 Disabled                 Enabled

## Omnibox Max Zero Suggest Matches

Changes the maximum number of autocomplete matches displayed when zero suggest is active (i.e. displaying suggestions without input). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-max-zero-suggest-matches](chrome://flags/#omnibox-max-zero-suggest-matches)

                   DefaultEnabledEnabled 5Enabled 6Enabled 7Enabled 8Enabled 9Enabled 10Enabled 11Enabled 12Enabled 13Enabled 14Enabled 15Disabled

                 Disabled                 Enabled

## Omnibox UI Max Autocomplete Matches

Changes the maximum number of autocomplete matches displayed in the Omnibox UI. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-ui-max-autocomplete-matches](chrome://flags/#omnibox-ui-max-autocomplete-matches)

                   DefaultEnabledEnabled 3 matchesEnabled 4 matchesEnabled 5 matchesEnabled 6 matchesEnabled 7 matchesEnabled 8 matchesEnabled 9 matchesEnabled 10 matchesEnabled 12 matchesDisabled

                 Disabled                 Enabled

## Omnibox Max URL Matches

The maximum number of URL matches to show, unless there are no replacements. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-max-url-matches](chrome://flags/#omnibox-max-url-matches)

                   DefaultEnabledEnabled 2 matchesEnabled 3 matchesEnabled 4 matchesEnabled 5 matchesEnabled 6 matchesDisabled

                 Disabled                 Enabled

## Omnibox Dynamic Max Autocomplete

Configures the maximum number of autocomplete matches displayed in the Omnibox UI dynamically based on the number of URL matches. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-dynamic-max-autocomplete](chrome://flags/#omnibox-dynamic-max-autocomplete)

                   DefaultEnabledEnabled 9 suggestions if 0 or fewer URLsEnabled 9 suggestions if 1 or fewer URLsEnabled 9 suggestions if 2 or fewer URLsEnabled 10 suggestions if 0 or fewer URLsEnabled 10 suggestions if 1 or fewer URLsEnabled 10 suggestions if 2 or fewer URLsDisabled

                 Disabled                 Enabled

## Retain Complete Set of Suggestions with Headers

Given a list of suggestions, all suggestions for which a header metadata is available will be retained as a whole and not be counted towards the limit. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-retain-suggestions-with-headers](chrome://flags/#omnibox-retain-suggestions-with-headers)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Bookmark Paths

Allows inputs to match with bookmark paths. E.g. 'planets jupiter' can suggest a bookmark titled 'Jupiter' with URL 'en.wikipedia.org/wiki/Jupiter' located in a path containing 'planet.' – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-bookmark-paths](chrome://flags/#omnibox-bookmark-paths)

                   DefaultEnabledEnabled Default UI (Title - URL)Enabled Replace title (Path/Title - URL)Enabled Replace URL (Title - Path)Enabled Append after title (Title : Path - URL)Enabled Dynamic Replace URL (Title - Path|URL)Disabled

                 Disabled                 Enabled

## Omnibox Short Bookmark Suggestions

Match very short input words to beginning of words in bookmark suggestions. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-short-bookmark-suggestions](chrome://flags/#omnibox-short-bookmark-suggestions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Optimization Guide Debug Logs

Enables the optimization guide to log and save debug messages that can be shown in the internals page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#optimization-guide-debug-logs](chrome://flags/#optimization-guide-debug-logs)

                 Disabled                 Enabled

## Organic Repeatable Queries in Most Visited Tiles

Enables showing the most repeated queries, from the device browsing history, organically among the most visited sites in the MV tiles. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#organic-repeatable-queries](chrome://flags/#organic-repeatable-queries)

                   DefaultEnabledEnabled - No max, High privilegeEnabled - No max, Low privilegeEnabled - Max 4, High privilegeEnabled - Max 4, Low privilegeDisabled

                 Disabled                 Enabled

## History Journeys

Enables the History Journeys UI. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys](chrome://flags/#history-journeys)

                   DefaultEnabledEnabled Sort Clusters Within Batch for QueryEnabled No 'Show More' - Drop hidden visitsEnabled No 'Show More' - Show all visitsEnabled All Supported LocalesDisabled

                 Disabled                 Enabled

## History Journeys Labels

Enables labels for Journeys within the History Journeys UI. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys-labels](chrome://flags/#history-journeys-labels)

                   DefaultEnabledEnabled With EntitiesEnabled With Entities, No HostnamesDisabled

                 Disabled                 Enabled

## History Journeys Omnibox Action

Enables the History Journeys Omnibox Action. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys-omnibox-action](chrome://flags/#history-journeys-omnibox-action)

                   DefaultEnabledEnabled Action Chips on All URLsEnabled Action Chips on Non-Noisy URLsEnabled Action Chips Enabled on Navigation IntentsEnabled Action Chips Enabled with PedalsDisabled

                 Disabled                 Enabled

## History Journeys Omnibox History Cluster Provider

Enables the History Journeys Omnibox History Cluster Provider to surface Journeys as a suggestion row instead of an action chip. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys-omnibox-history-cluster-provider](chrome://flags/#history-journeys-omnibox-history-cluster-provider)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## History Journeys On-Device Clustering Backend

Enables variations for the on-device clustering backend – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys-on-device-clustering](chrome://flags/#history-journeys-on-device-clustering)

                   DefaultEnabledEnabled No Content ClusteringEnabled Content ClusteringEnabled Show Single Domain JourneysEnabled Hide Single Domain JourneysDisabled

                 Disabled                 Enabled

## History Journeys On-Device Clustering Keyword Filtering

Enables variations for the keywords output by the on-device clustering for Journeys – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#history-journeys-on-device-clustering-keyword-filtering](chrome://flags/#history-journeys-on-device-clustering-keyword-filtering)

                   DefaultEnabledEnabled All VariationsEnabled No CategoriesEnabled No Noisy VisitsEnabled No Visit HostsEnabled With Search TermsDisabled

                 Disabled                 Enabled

## Page Content Annotations

Enables page content to be annotated on-device. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#page-content-annotations](chrome://flags/#page-content-annotations)

                   DefaultEnabledEnabled All Annotations and Persistence on ContentEnabled All Annotations and Persistence on TitleDisabled

                 Disabled                 Enabled

## Page Entities Content Annotations

Enables annotating the page entities model for each page load on-device. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#page-entities-page-content-annotations](chrome://flags/#page-entities-page-content-annotations)

                   DefaultEnabledEnabled All Supported LocalesDisabled

                 Disabled                 Enabled

## Page Visibility Content Annotations

Enables annotating the page visibility model for each page load on-device. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#page-visibility-page-content-annotations](chrome://flags/#page-visibility-page-content-annotations)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Block Insecure Private Network Requests

Prevents non-secure contexts from making subresource requests to more-private IP addresses. See also: <https://developer.chrome.com/blog/private-network-access-update/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#block-insecure-private-network-requests](chrome://flags/#block-insecure-private-network-requests)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Send Private Network Access Preflights

Enables sending Private Network Access preflights ahead of requests to more-private IP addresses. Failed preflights display warnings in DevTools without failing entire request. See also: <https://developer.chrome.com/blog/private-network-access-preflight/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#private-network-access-send-preflights](chrome://flags/#private-network-access-send-preflights)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Respect the Result of Private Network Access Preflights

Enables sending Private Network Access preflights ahead of requests to more-private IP addresses. These preflight requests must succeed in order for the request to proceed. See also: <https://developer.chrome.com/blog/private-network-access-preflight/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#private-network-access-respect-preflight-results](chrome://flags/#private-network-access-respect-preflight-results)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Reduce Waiting Time for Private Network Access Preflights Response

Reduce the waiting time for Private Network Access preflights to 200 milliseconds. The default timeout period for requests is 5 minutes.See also: <https://developer.chrome.com/blog/private-network-access-preflight/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#private-network-access-preflight-short-timeout](chrome://flags/#private-network-access-preflight-short-timeout)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## MBI Scheduling Mode

Enables independent agent cluster scheduling, via the AgentSchedulingGroup infrastructure. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#mbi-mode](chrome://flags/#mbi-mode)

                   DefaultEnabledEnabled legacy modeEnabled per render process hostEnabled per site instanceDisabled

                 Disabled                 Enabled

## Tab Groups 'New' Badge Promo

Causes a 'New' badge to appear on the entry point for creating a tab group in the tab context menu. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#tab-groups-new-badge-promo](chrome://flags/#tab-groups-new-badge-promo)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Tab Groups Save

Enables users to explicitly save and recall tab groups. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#tab-groups-save](chrome://flags/#tab-groups-save)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Tab Scrolling

Enables tab strip to scroll left and right when full. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#scrollable-tabstrip](chrome://flags/#scrollable-tabstrip)

                   DefaultEnabledEnabled  - tabs shrink to pinned tab widthEnabled  - tabs shrink to a medium widthEnabled  - tabs shrink to a large widthEnabled  - tabs don't shrinkDisabled

                 Disabled                 Enabled

## Split TabStrip

Splits pinned and unpinned tabs into separate TabStrips under the hood. Pure refactoring, no user-visible behavioral changes are included. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#split-tabstrip](chrome://flags/#split-tabstrip)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Side Panel Improved Clobbering

Improves the side panel clobbering experience for RHS side panels. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#side-panel-improved-clobbering](chrome://flags/#side-panel-improved-clobbering)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Side Panel Journeys

Enables Journeys within the side panel. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#side-panel-journeys](chrome://flags/#side-panel-journeys)

                   DefaultEnabledEnabled Omnibox opens Side Panel JourneysDisabled

                 Disabled                 Enabled

## Side Panel Webview

Adds a side panel option to load arbitrary web content, with a URL bar. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#side-panel-web-view](chrome://flags/#side-panel-web-view)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Unified Side Panel

Revamp the side panel experience. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#unified-side-panel](chrome://flags/#unified-side-panel)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Shopping List

Enable shopping list in bookmarks. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#shopping-list](chrome://flags/#shopping-list)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Chrome Cart Module

Shows the chrome cart module on the New Tab Page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-chrome-cart-module](chrome://flags/#ntp-chrome-cart-module)

                   DefaultEnabledEnabled - Fake Data And DiscountEnabled - Abandoned Cart DiscountEnabled - Heuristics ImprovementEnabled - RBD and CouponsDisabled

                 Disabled                 Enabled

## NTP Drive Module

Shows the Google Drive module on the New Tab Page – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-drive-module](chrome://flags/#ntp-drive-module)

                   DefaultEnabledEnabled - Fake DataEnabled - Managed Users OnlyDisabled

                 Disabled                 Enabled

## NTP Middle Slot Promo Dismissal

Allows middle slot promo to be dismissed from New Tab Page until new promo message is populated. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-middle-slot-promo-dismissal](chrome://flags/#ntp-middle-slot-promo-dismissal)

                   DefaultEnabledEnabled - Fake DataDisabled

                 Disabled                 Enabled

## NTP Modules Drag and Drop

Enables modules to be reordered via dragging and dropping on the New Tab Page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-modules-drag-and-drop](chrome://flags/#ntp-modules-drag-and-drop)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Modules First Run Experience

Shows first run experience for Modular NTP Desktop v1. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-modules-first-run-experience](chrome://flags/#ntp-modules-first-run-experience)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Modules Redesigned

Shows the redesigned modules on the New Tab Page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-modules-redesigned](chrome://flags/#ntp-modules-redesigned)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Ntp Modules Redesigned Layout

Changes the layout of modules on New Tab Page – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-modules-redesigned-layout](chrome://flags/#ntp-modules-redesigned-layout)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Photos Module

Shows the Google Photos module on the New Tab Page – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-photos-module](chrome://flags/#ntp-photos-module)

                   DefaultEnabledEnabled  - Fake memories: 0Enabled  - Fake memories: 1Enabled  - Fake memories: 2Enabled  - Fake memories: 3Enabled  - Fake memories: 4Disabled

                 Disabled                 Enabled

## NTP Photos Module Opt In ArtWork

Determines the art work in the NTP Photos Opt-In card – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-photos-opt-in-art-work](chrome://flags/#ntp-photos-opt-in-art-work)

                   DefaultEnabledEnabled  - Artwork with Logo - 1Enabled  - Artwork with Logo - 2Enabled  - Artwork with IllustrationsEnabled  - Artwork with StockpileDisabled

                 Disabled                 Enabled

## NTP Photos Module Opt In Title

Determines the title of the NTP Photos Opt-In card – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-photos-opt-in-title](chrome://flags/#ntp-photos-opt-in-title)

                   DefaultEnabledEnabled  - Recent HighlightsEnabled  - Favorite peopleEnabled  - Personalized titleEnabled  - Trips titleDisabled

                 Disabled                 Enabled

## NTP Photos Module Soft Opt-Out

Enables soft opt-out option in Photos opt-in card – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-photos-soft-opt-out](chrome://flags/#ntp-photos-soft-opt-out)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Recipe Tasks Module

Shows the recipe tasks module on the New Tab Page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-recipe-tasks-module](chrome://flags/#ntp-recipe-tasks-module)

                   DefaultEnabledEnabled - Fake DataEnabled - Historical Arm (7 days)Enabled - Historical Arm (14 days)Enabled - Recommended Mix Arm (7 days)Enabled - Recommended Mix Arm (14 days)Disabled

                 Disabled                 Enabled

## NTP Realbox Matches Omnibox Theme

NTP Realbox matches the Omnibox theme when enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-match-omnibox-theme](chrome://flags/#ntp-realbox-match-omnibox-theme)

                   DefaultEnabledEnabled (NTP background on steady state and Omnibox steady state background on hover)Enabled (NTP background on steady state and Omnibox active state background on hover)Disabled

                 Disabled                 Enabled

## NTP Realbox Matches Searchbox Theme

NTP Realbox matches the Searchbox theme when enabled. Specifically a border, drop shadow on hover. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-match-searchbox-theme](chrome://flags/#ntp-realbox-match-searchbox-theme)

                   DefaultEnabledEnabled (Rounded Corners)Disabled

                 Disabled                 Enabled

## NTP Realbox Pedals

Shows pedals in the NTP Realbox when enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-pedals](chrome://flags/#ntp-realbox-pedals)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Realbox Suggestion Answers

Shows suggestion answers in the NTP Realbox when enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-suggestion-answers](chrome://flags/#ntp-realbox-suggestion-answers)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Realbox Tail Suggest

Properly formats the tail suggestions to match the Omnibox – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-tail-suggest](chrome://flags/#ntp-realbox-tail-suggest)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## NTP Realbox Google G Icon

Shows Google G icon instead of Search Loupe in realbox when enabled – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#ntp-realbox-use-google-g-icon](chrome://flags/#ntp-realbox-use-google-g-icon)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Chrome-wide Echo Cancellation

Run WebRTC capture audio processing in the audio process instead of the renderer processes, thereby cancelling echoes from more audio sources. – Mac, Windows, Linux

[#chrome-wide-echo-cancellation](chrome://flags/#chrome-wide-echo-cancellation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Pixel Canvas Recording

Pixel canvas recording allows the compositor to raster contents aligned with the pixel and improves text rendering. This should be enabled when a device is using fractional scale factor. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-pixel-canvas-recording](chrome://flags/#enable-pixel-canvas-recording)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Parallel Downloading

Enable parallel downloading to accelerate download speed. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-parallel-downloading](chrome://flags/#enable-parallel-downloading)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Tab Hover Card Images

Shows a preview image in tab hover cards, if tab hover cards are enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#tab-hover-card-images](chrome://flags/#tab-hover-card-images)

                   DefaultEnabledEnabled  alternate hover card formatDisabled

                 Disabled                 Enabled

## Enable Network Logging to File

Enables network logging to a file named netlog.json in the user data directory. The file can be imported into chrome://net-internals. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-network-logging-to-file](chrome://flags/#enable-network-logging-to-file)

                 Disabled                 Enabled

## Web Authentication Enterprise Attestation

Permit a set of origins to request a uniquely identifying enterprise attestation statement from a security key when creating a Web Authentication credential. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#web-authentication-permit-enterprise-attestation](chrome://flags/#web-authentication-permit-enterprise-attestation)

                 Disabled                 Enabled

## Zero-copy Tab Capture

Enable zero-copy content tab for getDisplayMedia() APIs. – Mac

[#zero-copy-tab-capture](chrome://flags/#zero-copy-tab-capture)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Region Capture Experimental Subtypes

Enables experiment support for CropTarget.fromElement to use other Element subtypes than just `<div>` and `<iframe>`. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#region-capture-experimental-subtypes](chrome://flags/#region-capture-experimental-subtypes)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Accessible PDF Forms

Enables accessibility support for PDF forms. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#accessible-pdf-form](chrome://flags/#accessible-pdf-form)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## CUPS IPP Printing Backend

Use the CUPS IPP printing backend instead of the original CUPS backend that calls the PPD API. – Mac

[#cups-ipp-printing-backend](chrome://flags/#cups-ipp-printing-backend)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Insecure Origins Treated as Secure

Treat given (insecure) origins as secure origins. Multiple origins can be supplied as a comma-separated list. Origins must have their protocol specified e.g. "http://example.com". For the definition of secure contexts, see <https://w3c.github.io/webappsec-secure-contexts/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#unsafely-treat-insecure-origin-as-secure](chrome://flags/#unsafely-treat-insecure-origin-as-secure)

                 Disabled                 Enabled

## Disable Subframe Process Reuse

Prevents out-of-process iframes from reusing compatible processes from unrelated tabs. This is an experimental mode that will result in more processes being created. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#disable-process-reuse](chrome://flags/#disable-process-reuse)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Live Caption

Enables the live caption feature which generates captions for media playing in Chrome. Turn the feature on in chrome://settings/accessibility. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-accessibility-live-caption](chrome://flags/#enable-accessibility-live-caption)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Support Tool

Support Tool collects and exports logs to help debugging the issues. It's available in chrome://support-tool. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#support-tool](chrome://flags/#support-tool)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Auto-disable Accessibility

When accessibility APIs are no longer being requested, automatically disables accessibility. This might happen if an assistive technology is turned off or if an extension which uses accessibility APIs no longer needs them. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-auto-disable-accessibility](chrome://flags/#enable-auto-disable-accessibility)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Drop Input Events Before First Paint

Before the user can see the first paint of a new page they cannot intentionally interact with elements on that page. By dropping the events we prevent accidental interaction with a page the user has not seen yet. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#drop-input-events-before-first-paint](chrome://flags/#drop-input-events-before-first-paint)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Destroy Profile on Browser Close

Release memory and other resources when a Profile's last browser window is closed, rather than when Chrome closes completely. – Mac, Windows, Linux, Fuchsia, Lacros

[#destroy-profile-on-browser-close](chrome://flags/#destroy-profile-on-browser-close)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Destroy System Profile

After you close the Profile Picker, release memory and other resources owned by the System Profile. This requires #destroy-profile-on-browser-close. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#destroy-system-profiles](chrome://flags/#destroy-system-profiles)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Choose ANGLE Graphics Backend

Choose the graphics backend for ANGLE. The OpenGL backend is soon to be deprecated on Mac, and may contain driver bugs that are not planned to be fixed. The Metal backend is still experimental, and may contain bugs that are still being worked on. The Metal backend should be more performant, but may still be behind the OpenGL backend until fully released. – Mac

[#use-angle](chrome://flags/#use-angle)

                   DefaultOpenGLMetal

                 Disabled                 Enabled

## Desktop Screenshots

Enables taking screenshots from the desktop sharing hub. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#sharing-desktop-screenshots](chrome://flags/#sharing-desktop-screenshots)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop Screenshots Edit Mode

Enables an edit flow for users who create screenshots on desktop – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#sharing-desktop-screenshots-edit](chrome://flags/#sharing-desktop-screenshots-edit)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop Share Hub Preview

Adds a preview section to the desktop sharing hub to make it clearer what is about to be shared. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#sharing-desktop-share-preview](chrome://flags/#sharing-desktop-share-preview)

                   DefaultEnabledEnabled 16pt previewEnabled 40pt previewEnabled 72pt previewDisabled

                 Disabled                 Enabled

## Share to Google Collections

Adds an item to the sharing hub to allow sharing to Google Collections. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#sharing-desktop-share-to-google-collections](chrome://flags/#sharing-desktop-share-to-google-collections)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Gpu Service Logging

Enable printing the actual GL driver calls. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-gpu-service-logging](chrome://flags/#enable-gpu-service-logging)

                 Disabled                 Enabled

## Hardware Media Key Handling

Enables using media keys to control the active media session. This requires MediaSessionService to be enabled too – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#hardware-media-key-handling](chrome://flags/#hardware-media-key-handling)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## File Handling API

Enables the file handling API, allowing websites to register as file handlers. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#file-handling-api](chrome://flags/#file-handling-api)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## File Handling Icons

Allows websites using the file handling API to also register file type icons. See <https://github.com/WICG/file-handling/blob/main/explainer.md> for more information. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#file-handling-icons](chrome://flags/#file-handling-icons)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Strict-Origin-Isolation

Experimental security mode that strengthens the site isolation policy. Controls whether site isolation should use origins instead of scheme and eTLD+1. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#strict-origin-isolation](chrome://flags/#strict-origin-isolation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable the `<fencedframe>` Element

Fenced frames are an experimental web platform feature that allows embedding an isolated top-level page. This requires #privacy-sandbox-ads-apis to also be enabled. See <https://github.com/shivanigithub/fenced-frame> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-fenced-frames](chrome://flags/#enable-fenced-frames)

                   DefaultEnabledEnabled with ShadowDOMEnabled with multiple page architectureDisabled

                 Disabled                 Enabled

## Enable Portals

Portals are an experimental web platform feature that allows embedding and seamless transitions between pages. See <https://github.com/WICG/portals> and <https://wicg.github.io/portals/> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-portals](chrome://flags/#enable-portals)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Cross-origin Portals

Allows portals to load cross-origin URLs in addition to same-origin ones. Has no effect if Portals are not enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-portals-cross-origin](chrome://flags/#enable-portals-cross-origin)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Using Platform Authenticators to Retrieve Server Cards

When enabled, users will be given the option to use a platform authenticator (if available) to verify card ownership when retrieving credit cards from Google Payments. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-autofill-credit-card-authentication](chrome://flags/#enable-autofill-credit-card-authentication)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Storage Access API

Enables the Storage Access API, allowing websites to request storage access when it would otherwise be restricted. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#storage-access-api](chrome://flags/#storage-access-api)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## WebGPU Developer Features

Enables web applications to access WebGPU features intended only for use during development. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-webgpu-developer-features](chrome://flags/#enable-webgpu-developer-features)

                 Disabled                 Enabled

## Font Access APIs

Enables the experimental Font Access APIs, giving websites access to enumerate local fonts and access their table data. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#font-access](chrome://flags/#font-access)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Global Media Controls Modern UI

Use a redesigned version of the Global Media Controls UI. Requires #global-media-controls to also be enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#global-media-controls-modern-ui](chrome://flags/#global-media-controls-modern-ui)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Support for HTTPS Records in DNS

When enabled, Chrome may query for HTTPS records in DNS. If any are found, Chrome may upgrade the URL to HTTPS or enable Encrypted ClientHello, depending on server support and whether those features are enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#dns-https-svcb](chrome://flags/#dns-https-svcb)

                   DefaultEnabledEnabled for DNS-over-HTTPS and insecure DNSEnabled for DNS-over-HTTPS onlyDisabled

                 Disabled                 Enabled

## Encrypted ClientHello

When enabled, Chrome will enable Encrypted ClientHello support. This will encrypt TLS ClientHello if the server enables the extension via the HTTPS DNS record. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#encrypted-client-hello](chrome://flags/#encrypted-client-hello)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use DNS Https Alpn

When enabled, Chrome may try QUIC on the first connection using the ALPN information in the DNS HTTPS record. – Mac, Windows, Linux, ChromeOS, Android

[#use-dns-https-svcb-alpn](chrome://flags/#use-dns-https-svcb-alpn)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Web Bundles

Enables experimental supports for Web Bundles (Bundled HTTP Exchanges) navigation. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#web-bundles](chrome://flags/#web-bundles)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## HiDPI Tab Capture

Enables HiDPI rendering for tab capture if the displayed content's resolution is low compared to the capture size. This improves legibility for viewers with higher-resolution screens. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#hidpi-capture](chrome://flags/#hidpi-capture)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Offer Save and Autofill of UPI/VPA Values

If enabled, when autofill recognizes a UPI/VPA value in a payment form, it will offer to save it. If saved, it will be offered for filling in fields which expect a VPA. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-autofill-upi-vpa](chrome://flags/#enable-autofill-upi-vpa)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Return Cloud Token Details for Server Credit Cards When Possible

When enabled and where available, forms filled using Google Payments server cards are populated with cloud token details, including CPAN (cloud tokenized version of the Primary Account Number) and dCVV (dynamic CVV). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-always-return-cloud-tokenized-card](chrome://flags/#autofill-always-return-cloud-tokenized-card)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Back-forward Cache

If enabled, caches eligible pages after cross-site navigations.To enable caching pages on same-site navigations too, choose 'enabled same-site support'. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#back-forward-cache](chrome://flags/#back-forward-cache)

                   DefaultEnabledEnabled force caching all pages (experimental)Disabled

                 Disabled                 Enabled

## Enable Back-forward Cache for Screen Readers

If enabled, allow pages to enter back/forward cache even if a screen reader is in use. The page might still not be cached for other reasons. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-back-forward-cache-for-screen-reader](chrome://flags/#enable-back-forward-cache-for-screen-reader)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Closed Tab Cache

Enables closed tab cache to instantaneously restore recently closed tabs. NOTE: This feature is higly experimental and will lead to various breakages, enable at your own risk. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#closed-tab-cache](chrome://flags/#closed-tab-cache)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Windows Scrolling Personality

If enabled, mousewheel and keyboard scrolls will scroll by a percentage of the scroller size and the default scroll animation is replaced with Impulse-style scroll animations. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#windows-scrolling-personality](chrome://flags/#windows-scrolling-personality)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Scroll Unification

Refactoring project that eliminates scroll handling code from Blink. Does not affect behavior or performance. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#scroll-unification](chrome://flags/#scroll-unification)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Device Posture API

Enables Device Posture API (foldable devices) – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#device-posture](chrome://flags/#device-posture)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Screen Time

Integrate with the macOS Screen Time system. Only enabled on macOS 12.1 and later. – Mac

[#screentime](chrome://flags/#screentime)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Offer to Use Cloud Token Virtual Card in Autofill

When enabled, if all requirements are met, Autofill will offer to use virtual credit cards in form filling. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#autofill-enable-virtual-card](chrome://flags/#autofill-enable-virtual-card)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Showing Card Product Name

When enabled, card product name (instead of issuer network) will be shown in Payments UI. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-card-product-name](chrome://flags/#autofill-enable-card-product-name)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Full User-Agent Request Header

If set, use the full (non-reduced) user agent string for the User-Agent request header and the JS APIs. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#full-user-agent](chrome://flags/#full-user-agent)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Reduce User-Agent Request Header

Reduce (formerly, "freeze") the amount of information available in the User-Agent request header. See <https://www.chromium.org/updates/ua-reduction> for more info. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#reduce-user-agent](chrome://flags/#reduce-user-agent)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Disruptive Notification Permission Revocation

Enables revoking the notification permission on sites that send disruptive notifications unless the permission was granted through a prompt that informed the user about this possibility. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#disruptive-notification-permission-revocation](chrome://flags/#disruptive-notification-permission-revocation)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Fetch Credentials' Password Change Capabilities

Fetches credentials' password change capabilities from the server. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#password-domain-capabilities-fetching](chrome://flags/#password-domain-capabilities-fetching)

                   DefaultEnabledEnabled Live experimentDisabled

                 Disabled                 Enabled

## Force Enable Password Change Capabilities for Domains

Force enables password change capabilities for every domain, regardless of the server response. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-enable-password-domain-capabilities](chrome://flags/#force-enable-password-domain-capabilities)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Rework Password Change Flow

Change password when password leak is detected. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#password-change-support](chrome://flags/#password-change-support)

                   DefaultEnabledEnabled Force dialog after every successful form submission.Disabled

                 Disabled                 Enabled

## Rework Password Change Flow From Settings

Change password when bulk leak check detected an issue. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#password-change-in-settings](chrome://flags/#password-change-in-settings)

                   DefaultEnabledEnabled Force leak warnings for every site in settings.Enabled Include weak credentials.Disabled

                 Disabled                 Enabled

## Page Info Hide Site Settings

Hides site settings row in the page info menu. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#page-info-hide-site-settings](chrome://flags/#page-info-hide-site-settings)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Page Info History

Enable a history section in the page info. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#page-info-history-desktop](chrome://flags/#page-info-history-desktop)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## 'More About This Page' Link in Page Info

Enable the 'More about this page' link in the 'From the web' section of page info. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#page-info-more-about-this-page](chrome://flags/#page-info-more-about-this-page)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## AboutThisPage Description Placeholder

Shows a placeholder when no description is availble instead of not showing an entry at all – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#page-info-about-this-page-description-placeholder](chrome://flags/#page-info-about-this-page-description-placeholder)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## AboutThisPage Persistent SidePanel Entry

Registers a SidePanel entry on pageload if 'AboutThisPage' info is available – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#page-info-about-this-page-persistent-side-panel-entry](chrome://flags/#page-info-about-this-page-persistent-side-panel-entry)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Color Provider Redirection For Theme Provider

Redirects color requests from the ThemeProvider to the ColorProvider where possible. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#color-provider-redirection-for-theme-provider](chrome://flags/#color-provider-redirection-for-theme-provider)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Refactoring Shared Highlighting

Refactors Shared Highlighting by centralizing the IPC calls in a Manager. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#shared-highlighting-manager](chrome://flags/#shared-highlighting-manager)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Shared Highlighting Blocklist Refinement

Narrow the Blocklist for enabling Shared Highlighting. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#shared-highlighting-refined-blocklist](chrome://flags/#shared-highlighting-refined-blocklist)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Shared Highlighting Max Context Words Refinement

Experiment with different Max Context Words for Shared Highlighting. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#shared-highlighting-refined-maxcontextwords](chrome://flags/#shared-highlighting-refined-maxcontextwords)

                   DefaultEnabledEnabled  - maxContextWords: 5Enabled  - maxContextWords: 10Enabled  - maxContextWords: 15Enabled  - maxContextWords: 20Disabled

                 Disabled                 Enabled

## Enable Experimental Cookie Features

Enable new features that affect setting, sending, and managing cookies. The enabled features are subject to change at any time. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-experimental-cookie-features](chrome://flags/#enable-experimental-cookie-features)

                   DefaultEnabled

                 Disabled                 Enabled

## Permissions Chip Experiment

Enables an experimental permission prompt that uses a chip in the location bar. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#permission-chip](chrome://flags/#permission-chip)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Gesture-sensitive Permissions Chip

If the Permissions Chip Experiment is enabled, controls whether or not the chip should be more prominent when the request is associated with a gesture. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#permission-chip-gesture](chrome://flags/#permission-chip-gesture)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Request-type-sensitive Permissions Chip

If the Permissions Chip Experiment is enabled, controls whether or not the chip should be more or less prominent depending on the request type. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#permission-chip-request-type](chrome://flags/#permission-chip-request-type)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Quiet Permission Chip Experiment

Enables a permission prompt that uses the quiet chip instead of the right-hand side address bar icon for quiet permission prompts. Requires chrome://flags/#quiet-notification-prompts to be enabled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#permission-quiet-chip](chrome://flags/#permission-quiet-chip)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enables Canvas 2D Methods BeginLayer and EndLayer

Enables the canvas 2D methods BeginLayer and EndLayer. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#canvas-2d-layers](chrome://flags/#canvas-2d-layers)

                 Disabled                 Enabled

## Enables Machine Learning Model Loader Web Platform API

Enables the Machine Learning Model Loader Web Platform API. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-machine-learning-model-loader-web-platform-api](chrome://flags/#enable-machine-learning-model-loader-web-platform-api)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Translate Sub Frames

Enable the translation of sub frames (as well as the main frame) – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-translate-sub-frames](chrome://flags/#enable-translate-sub-frames)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Attribution Reporting Debug Mode

Enables debug mode for the Attribution Reporting API. This removes all reporting delays and noise. Only works if the Attribution Reporting API is already enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#attribution-reporting-debug-mode](chrome://flags/#attribution-reporting-debug-mode)

                 Disabled                 Enabled

## Enable Bluetooth Serial Port Profile in Serial API

When enabled, Bluetooth Serial Port Profile devices will be enumerated for use with the Serial API. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-bluetooth-spp-in-serial-api](chrome://flags/#enable-bluetooth-spp-in-serial-api)

                 Disabled                 Enabled

## Password View Page in Settings

Enables a new password details subpage in the settings password management UI. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#password-view-page-in-settings](chrome://flags/#password-view-page-in-settings)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Password Notes in Settings

Enables a note section for each password in the settings page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#password-notes](chrome://flags/#password-notes)

                   DefaultEnabledEnabled - Authentication expires after 1 minute of inactivityEnabled - Authentication expires after 5 minutes of inactivityDisabled

                 Disabled                 Enabled

## Enable JXL Image Format

Adds image decoding support for the JPEG XL image format. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-jxl](chrome://flags/#enable-jxl)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Quick Commands

Enable a text interface to browser features. Invoke with Ctrl-Space. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#quick-commands](chrome://flags/#quick-commands)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable PWA Install Update Dialog for Icon Changes

Enable a confirmation dialog that shows up when a PWA changes its icon – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#pwa-update-dialog-for-icon](chrome://flags/#pwa-update-dialog-for-icon)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable PWA Install Update Dialog for Name Changes

Enable a confirmation dialog that shows up when a PWA changes its name – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#pwa-update-dialog-for-name](chrome://flags/#pwa-update-dialog-for-name)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enables Out-of-Process Printer Drivers

Enables printing interactions with the operating system to be performed out-of-process. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-oop-print-drivers](chrome://flags/#enable-oop-print-drivers)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Privacy Sandbox V3

Enables an updated Privacy Sandbox UI. Also enables some related features. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#privacy-sandbox-v3-desktop](chrome://flags/#privacy-sandbox-v3-desktop)

                 Disabled                 Enabled

## Privacy Sandbox Ads APIs

Enables Privacy Sandbox APIs: Attribution Reporting, Fledge, Topics, Fenced Frames, Shared Storage, Private Aggregation, and their associated features. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#privacy-sandbox-ads-apis](chrome://flags/#privacy-sandbox-ads-apis)

                 Disabled                 Enabled

## Deferred Font Shaping

Defer text rendering in invisible CSS boxes until the boxes become visible. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#deferred-font-shaping](chrome://flags/#deferred-font-shaping)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Permission Predictions

Use the Permission Predictions Service to surface permission requests using a quieter UI when the likelihood of the user granting the permission is predicted to be low. Requires chrome://flags/#quiet-notification-prompts and `Safe Browsing` to be enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#permission-predictions](chrome://flags/#permission-predictions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Show Performance Metrics in HUD

Display the performance metrics of current page in a heads up display on the page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#show-performance-metrics-hud](chrome://flags/#show-performance-metrics-hud)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Prerender2

Enables the new prerenderer implementation for `<script type=speculationrules>` that specifies prerender candidates. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-prerender2](chrome://flags/#enable-prerender2)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Trigger for Prerender2

Enables the new omnibox trigger prerenderer implementation. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-trigger-for-prerender2](chrome://flags/#omnibox-trigger-for-prerender2)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Prerender Search Suggestions

Allows Prerender2 to prerender search suggestions provided by the default search engine. Requires chrome://flags/#enable-prerender2 to be enabled – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#search-suggestion-for-prerender2](chrome://flags/#search-suggestion-for-prerender2)

                   DefaultEnabledEnabled use prefetched requestEnabled ignore prefetched requestDisabled

                 Disabled                 Enabled

## Chrome Labs

Access Chrome Labs through the toolbar menu to see featured user-facing experimental features. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#chrome-labs](chrome://flags/#chrome-labs)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable First-Party Sets

When enabled, Chrome will apply First-Party Sets to features such as the SameParty cookie attribute. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-first-party-sets](chrome://flags/#enable-first-party-sets)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Performs OCR on Inaccessible PDFs

Enables a feature whereby inaccessible (i.e. untagged) PDFs are made accessible using an optical character recognition service. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#pdf-ocr](chrome://flags/#pdf-ocr)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## PDF XFA Support

Enables support for XFA forms in PDFs. Has no effect if Chrome was not built with XFA support. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#pdf-xfa-forms](chrome://flags/#pdf-xfa-forms)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Send Tab to Self Sign-in Promo

Enables a sign-in promo if the user attempts to share a tab while being signed out – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#send-tab-to-self-signin-promo](chrome://flags/#send-tab-to-self-signin-promo)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Clear Window Name in Top-level Cross-site Cross-browsing-context-group Navigation

Clear the preserved window.name property when it's a top-level cross-site navigation that swaps BrowsingContextGroup. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#clear-cross-site-cross-browsing-context-group-window-name](chrome://flags/#clear-cross-site-cross-browsing-context-group-window-name)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Hardware Decode Acceleration for k-SVC VP9

Enable or disable k-SVC VP9 hardware decode acceleration – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-vp9-kSVC-decode-acceleration](chrome://flags/#enable-vp9-kSVC-decode-acceleration)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Debugging Tools for UI

Enables additional keyboard shortcuts to help debugging. – Mac, Windows, Linux, Fuchsia, Lacros

[#ui-debug-tools](chrome://flags/#ui-debug-tools)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Detailed Language Settings (Desktop)

Enable the new detailed language settings page – Mac, Windows, Linux, Fuchsia, Lacros

[#desktop-detailed-language-settings](chrome://flags/#desktop-detailed-language-settings)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Sync Promo After Sign-in Intercept

Enable updates in the first run experience for a new profile in the Sign-in Intercept, such as a Sync Promo step and an updated Profile Customization UI, which is also used for local profile creation. – Mac, Windows, Linux, Fuchsia, Lacros

[#sync-promo-after-signin-intercept](chrome://flags/#sync-promo-after-signin-intercept)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Sign-in Intercept Bubble V2

Enable visual updates to the sign-in intercept bubble, such as updated illustration, strings and an enterprise disclaimer. – Mac, Windows, Linux, Fuchsia, Lacros

[#signin-intercept-bubble-v2](chrome://flags/#signin-intercept-bubble-v2)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Fill Passwords Across Affiliated Websites

Enables filling password on a website when there is saved password on affiliated website. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#filling-across-affiliated-websites](chrome://flags/#filling-across-affiliated-websites)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## FedCM

Enables JavaScript API to intermediate federated identity requests. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#fedcm](chrome://flags/#fedcm)

                   DefaultEnabledEnabled - with FedCM auto sign-inEnabled - with FedCM IDP sign-outEnabled - with iframe supportEnabled - with FedCM IDP sign-in statusDisabled

                 Disabled                 Enabled

## FedCmMultiIdp

Allows the FedCM API to request multiple identity providers simultaneously. Requires FedCM to be enabled as well. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#fedcm-multi-idp](chrome://flags/#fedcm-multi-idp)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Parse Promo Code Fields in Forms

When enabled, Autofill will attempt to find merchant promo/coupon/gift code fields when parsing forms. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-parse-merchant-promo-code-fields](chrome://flags/#autofill-parse-merchant-promo-code-fields)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Sanitizer API

Enable the Sanitizer API. See: <https://github.com/WICG/sanitizer-api> – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sanitizer-api](chrome://flags/#sanitizer-api)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Sanitizer API, Initial Version

Enable the initial version of the Sanitizer API. This includes the Element.setHTML method, but not any sanitization methods on the Sanitizer instances. See also the #sanitizer-api flag. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sanitizer-api-v0](chrome://flags/#sanitizer-api-v0)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Prevent Autofill From Overriding Prefilled Field Values

When enabled, Autofill won't override any field values that have not been filled by Autofill – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-prevent-overriding-prefilled-values](chrome://flags/#autofill-prevent-overriding-prefilled-values)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Show Autofill Options in Context Menu

When enabled, users would get address/credit cards/passwords autofilling options in the context menu if the context menu is opened on a text field – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#autofill-show-manual-fallbacks-in-context-menu](chrome://flags/#autofill-show-manual-fallbacks-in-context-menu)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Lens Fullscreen Search Features

Enables Lens fullscreen search features. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-lens-fullscreen-search](chrome://flags/#enable-lens-fullscreen-search)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Lens Features in Chrome

Enables Lens image and region search to learn about the visual content you see while you browse and shop on the web. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-lens-standalone](chrome://flags/#enable-lens-standalone)

                   DefaultEnabledEnabled With Side PanelDisabled

                 Disabled                 Enabled

## Enable Improvements to the Lens Instruction Chip

Enables improvements to the Lens instruction chip when using the region search feature. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-lens-instruction-chip-improvements](chrome://flags/#enable-lens-instruction-chip-improvements)

                   DefaultEnabledEnabled With Image Selection IconEnabled With Alt TextDisabled

                 Disabled                 Enabled

## Enable Region Search on PDF Viewer

Enable the Lens Region Search feature on the PDF viewer. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-region-search-on-pdf-viewer](chrome://flags/#enable-region-search-on-pdf-viewer)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Update History Entry Points in Incognito

When enabled, the entry points to history UI from Incognito mode will be removed for iOS and Desktop. An educative placeholder will be shown for Android history page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#update-history-entry-points-in-incognito](chrome://flags/#update-history-entry-points-in-incognito)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Align Delayed Wake Ups at 125 Hz

Run most delayed tasks with a non-zero delay (including DOM Timers) on a periodic 125Hz tick, instead of as soon as their delay has passed. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#align-wakeups](chrome://flags/#align-wakeups)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Throttle Non-visible Cross-origin Iframes

When enabled, all cross-origin iframes with zero visibility (either display:none or zero viewport intersection with non-zero area) will be throttled, regardless of whether they are same-process or cross-process. When disabled, throttling for cross-process iframes is the same, but for same-process iframes throttling only occurs when the frame has zero viewport intersection, a non-zero area, and is not display:none. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-throttle-display-none-and-visibility-hidden-cross-origin-iframes](chrome://flags/#enable-throttle-display-none-and-visibility-hidden-cross-origin-iframes)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use Passthrough Command Decoder

Use chrome passthrough command decoder instead of validating command decoder. – Mac, Linux, ChromeOS, Android, Fuchsia, Lacros

[#use-passthrough-command-decoder](chrome://flags/#use-passthrough-command-decoder)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Password Strength Indicator

Enables password strength indicator when typing a password during a sign-up and password change flows. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#password-strength-indicator](chrome://flags/#password-strength-indicator)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Privacy Guide V2

Enables UI updates for Privacy Guide. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#privacy-guide-2](chrome://flags/#privacy-guide-2)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Extension Request Justification

Enables users to justify their extension requests by causing a text field to appear on the extension request dialog. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#extension-workflow-justification](chrome://flags/#extension-workflow-justification)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Fuzzy Search for Tab Search

Enable fuzzy search for Tab Search. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#tab-search-fuzzy-search](chrome://flags/#tab-search-fuzzy-search)

                   DefaultEnabledEnabled  - fuzzy level: smallEnabled  - fuzzy level: mediumEnabled  - fuzzy level: largeDisabled

                 Disabled                 Enabled

## Show Chrome What's New Page at chrome://whats-new

Enables Chrome What's New page at chrome://whats-new. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#chrome-whats-new-ui](chrome://flags/#chrome-whats-new-ui)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Promos for Sync Trusted Vault Passphrase

Enables promos for an experimental sync passphrase type, referred to as trusted vault. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sync-trusted-vault-passphrase-promo](chrome://flags/#sync-trusted-vault-passphrase-promo)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Sync Trusted Vault Passphrase with Improved Recovery

Enables support for an experimental sync passphrase type, referred to as trusted vault, including logic and APIs for improved account recovery flows. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sync-trusted-vault-passphrase-recovery](chrome://flags/#sync-trusted-vault-passphrase-recovery)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use Sync Standalone Invalidations

If enabled, Sync will use standalone invalidations instead of topic based invalidations (Wallet and Offer data types are enabled by a dedicated flag). – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sync-standalone-invalidations](chrome://flags/#sync-standalone-invalidations)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Use Sync Standalone Invalidations for Wallet and Offer

If enabled, Sync will use standalone invalidations for Wallet and Offer data types. Takes effect only when Sync standalone invalidations are enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sync-standalone-invalidations-wallet-and-offer](chrome://flags/#sync-standalone-invalidations-wallet-and-offer)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Consider SameParty Cookies to Be First-party

If enabled, SameParty cookies will not be blocked even if third-party cookies are blocked. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sameparty-cookies-considered-first-party](chrome://flags/#sameparty-cookies-considered-first-party)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Partitioned Cookies

Controls if the Partitioned cookie attribute is enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#partitioned-cookies](chrome://flags/#partitioned-cookies)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Partitioned Cookies: Bypass Origin Trial

If this flag is enabled, Chrome will not require a site to opt into the origin trial in order to send or receive cookies set with the Partitioned attribute. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#partitioned-cookies-bypass-origin-trial](chrome://flags/#partitioned-cookies-bypass-origin-trial)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Nonced Partitioned Cookies Only

When this flag is enabled, we allow partitioned cookies whose partition keys contain a nonce even if the "Partitioned cookies" feature is disabled. If "Partitioned cookies" are enabled, then enabling or disabling this feature does nothing. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#nonced-partitioned-cookies](chrome://flags/#nonced-partitioned-cookies)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Experimental Third-party Storage Partitioning

Enables partitioning of third-party storage by top-level site. Note: this is under active development and may result in unexpected behavior. Please file bugs at <https://bugs.chromium.org/p/chromium/issues/entry?labels=StoragePartitioning-trial-bugs&components=Blink%3EStorage>. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#third-party-storage-partitioning](chrome://flags/#third-party-storage-partitioning)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omnibox Updated Connection Security Indicators

Use new connection security indicators for https pages in the omnibox. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omnibox-updated-connection-security-indicators](chrome://flags/#omnibox-updated-connection-security-indicators)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enables Display Compositor to Use a New Gpu Thread

When enabled, chrome uses 2 gpu threads instead of 1. Display compositor uses new dr-dc gpu thread and all other clients (raster, webgl, video) continues using the gpu main thread. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-drdc](chrome://flags/#enable-drdc)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Force GPU Main Thread Priority to Normal for DrDc

When enabled, force GPU main thread priority to be normal for DrDc mode. In that case DrDc thread continues to use DISPLAY thread priority and hence have higher thread priority than GPU main. Note that this flag will be a no-op when DrDc is disabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-gpu-main-thread-to-normal-priority-drdc](chrome://flags/#force-gpu-main-thread-to-normal-priority-drdc)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Autofill of Promo Code Fields in Forms

When enabled, Autofill will attempt to fill merchant promo/coupon/gift code fields when data is available. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-fill-merchant-promo-code-fields](chrome://flags/#autofill-fill-merchant-promo-code-fields)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Extensions Menu Access Control

Enables a redesigned extensions menu that allows the user to control extensions site access. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#extensions-menu-access-control](chrome://flags/#extensions-menu-access-control)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## window.PERSISTENT Is Temporary Quota

Causes the window.PERSISTENT quota type to have the same semantics as window.TEMPORARY. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#persistent-quota-is-temporary-quota](chrome://flags/#persistent-quota-is-temporary-quota)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Out-of-process 2D Canvas Rasterization

The rasterization of 2d canvas contents is performed in the GPU process. Requires that out-of-process rasterization be enabled. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#canvas-oop-rasterization](chrome://flags/#canvas-oop-rasterization)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Tab Audio Muting UI Control

When enabled, the audio indicators in the tab strip double as tab audio mute controls. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-tab-audio-muting](chrome://flags/#enable-tab-audio-muting)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Load the CryptoToken Component Extension

Enable this flag to temporarily work around issues with `chrome.runtime` being undefined as a side effect of U2F API removal. This workaround will go away with Chrome 107. Websites should not depend on `chrome.runtime` or `chrome.app` being defined unconditionally. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#load-cryptotoken-extension](chrome://flags/#load-cryptotoken-extension)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Put Major Version in Minor Version Position in User-Agent

Lock the Chrome major version in the User-Agent string to 99, and force the major version number to the minor version position. This flag is a backup plan for unexpected site-compatibility breakage with a three digit major version. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#force-major-version-to-minor](chrome://flags/#force-major-version-to-minor)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Extend Autofill Offers and Rewards Notification to Promo Code Offers

When enabled, a notification will be displayed on page navigation if the domain has an eligible merchant promo code offer or reward. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-offer-notification-for-promo-codes](chrome://flags/#autofill-enable-offer-notification-for-promo-codes)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Upcoming Sharing Features

This flag enables all upcoming sharing features, in the experiment arms that are most likely to be shipped. This is a meta-flag so which features are upcoming at any given time may change. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#upcoming-sharing-features](chrome://flags/#upcoming-sharing-features)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Side Search

Enables an easily accessible way to access your most recent Google search results page embedded in a browser side panel – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#side-search](chrome://flags/#side-search)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Side Search DSE Support

Side search with support for participating chrome search engines. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#side-search-dse-support](chrome://flags/#side-search-dse-support)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Search Web in Side Panel

Displays right-click search results of a highlighted text in side panel – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#search-web-in-side-panel](chrome://flags/#search-web-in-side-panel)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Customize Chrome Side Panel

Enables the ability to use Customize Chrome functionality from the unified side panel on the New Tab Page. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#customize-chrome-side-panel](chrome://flags/#customize-chrome-side-panel)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Raw Draw

When enabled, web content will be rastered on output surface directly. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-raw-draw](chrome://flags/#enable-raw-draw)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Document Picture-in-Picture API

Enables API to open an always-on-top window with a full HTML document – Mac, Windows, Linux, ChromeOS

[#document-picture-in-picture-api](chrome://flags/#document-picture-in-picture-api)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Web MIDI

Enables the implementation of the Web MIDI API. When disabled the interface will still be exposed by Blink. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#web-midi](chrome://flags/#web-midi)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Commerce Developer Mode

Allows users in the allowlist to enter the developer mode – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-commerce-developer](chrome://flags/#enable-commerce-developer)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Update Virtual Card Enrollment

When enabled, the user will have the ability to update the virtual card enrollment of a credit card through their chrome browser after certain autofill flows (for example, downstream and upstream), and from the settings page. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-update-virtual-card-enrollment](chrome://flags/#autofill-enable-update-virtual-card-enrollment)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Dialogs to Notify the User of Safe Browsing Enhanced Protection

Enable the use of dialogs to notify the user of Safe Browsing Enhanced Protection within Chrome when they enable or disable Enhanced Protection on their Account. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-tailored-security-desktop-notice](chrome://flags/#enable-tailored-security-desktop-notice)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Screen AI

Enables Screen AI local machine intelligence library to use the screen snapshots to add metadata for accessibility tools. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#screen-ai](chrome://flags/#screen-ai)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Virtual Card Enrollment Management in Desktop Payments Settings Page

When enabled, chrome://settings/payments will offer the option to enroll in virtual card if the card is eligible and to unenroll if the card has been enrolled. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#autofill-enable-virtual-card-management-in-desktop-settings-page](chrome://flags/#autofill-enable-virtual-card-management-in-desktop-settings-page)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Origin-keyed Agent Clusters by Default

Select the default behaviour for the Origin-Agent-Cluster http header. If enabled, an absent header will cause pages to be assigned to an origin-keyed agent cluster, and to a site-keyed agent cluster when disabled. Documents whose agent clusters are origin-keyed cannot set document.domain to relax the same-origin policy. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#origin-agent-cluster-default](chrome://flags/#origin-agent-cluster-default)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Sending Billing Customer Number in GetUploadDetails

When enabled the billing customer number will be sent in the GetUploadDetails preflight calls. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-sending-bcn-in-get-upload-details](chrome://flags/#autofill-enable-sending-bcn-in-get-upload-details)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## When Enabled, Sets Non-legacy Instrument ID in UnmaskCardRequest

When enabled, UnmaskCardRequest will set the card's non-legacy ID when available. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-unmask-card-request-set-instrument-id](chrome://flags/#autofill-enable-unmask-card-request-set-instrument-id)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Persistent Client Hints

Persist the client hints cache beyond browser restarts. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#durable-client-hints-cache](chrome://flags/#durable-client-hints-cache)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## EditContext API

Allows web pages to use the experimental EditContext API to better control text input. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#edit-context](chrome://flags/#edit-context)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Isolated Sandboxed Iframes

When enabled, applies process isolation to iframes with the 'sandbox' attribute and without the 'allow-same-origin' permission set on that attribute. This also applies to documents with a similar CSP sandbox header, even in the main frame. The affected sandboxed documents can be grouped into processes based on their URL's site or origin. The default grouping when enabled is per-site. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-isolated-sandboxed-iframes](chrome://flags/#enable-isolated-sandboxed-iframes)

                   DefaultEnabledEnabled with grouping by URL's siteEnabled with grouping by URL's originEnabled with each sandboxed frame document in its own processDisabled

                 Disabled                 Enabled

## Enable Download Bubble

Enables the download bubble instead of the download shelf. – Mac, Windows, Linux, Lacros

[#download-bubble](chrome://flags/#download-bubble)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Download Bubble V2

Adds features to the download bubble not available on the download shelf. Only works if the base download bubble flag download-bubble is also enabled. – Mac, Windows, Linux, Lacros

[#download-bubble-v2](chrome://flags/#download-bubble-v2)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Increase the Nesting Threshold Before Which setTimeout(…, <4ms) Start Being Clamped

setTimeout(…, 0) is commonly used to break down long Javascript tasks. Under this flag, setTimeouts and setIntervals with an interval < 4ms are not clamped as aggressively. This improves short horizon performance, but websites abusing the API will still eventually have their setTimeouts clamped. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#unthrottled-nested-timeout](chrome://flags/#unthrottled-nested-timeout)

                   DefaultEnabledEnabled 100Disabled

                 Disabled                 Enabled

## Reduce Accept-Language Request Header

Reduce the amount of information available in the Accept-Language request header. See <https://github.com/Tanych/accept-language> for more info. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#reduce-accept-language](chrome://flags/#reduce-accept-language)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Reduce the Minor Version in the User-Agent String

Reduce the minor, build, and patch versions in the User-Agent string. The Chrome version in the User-Agent string will be reported as Chrome/<major_version>.0.0.0. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#reduce-user-agent-minor-version](chrome://flags/#reduce-user-agent-minor-version)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Reduce the Plaftform and Oscpu in the Desktop User-Agent String

Reduce the plaftform and oscpu in the desktop User-Agent string. The platform and oscpu in the User-Agent string will be reported as `<unifiedPlatform>` – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#reduce-user-agent-platform-oscpu](chrome://flags/#reduce-user-agent-platform-oscpu)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allows Access to WebSQL APIs

The WebSQL API is enabled by default, but can be disabled here. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#web-sql-access](chrome://flags/#web-sql-access)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Omit TLS Client Certificates if Credential Mode Disallows

Strictly conform the Fetch spec to omit TLS client certificates if credential mode disallows. Without this flag enabled, Chrome will always try sending client certificates regardless of the credential mode. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#omit-cors-client-cert](chrome://flags/#omit-cors-client-cert)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enforce Delay Between Offering Autofill Opportunities in the Strike Database

When enabled, if previous Autofill feature offer was declined, Chrome will wait for some time before showing the offer again. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enforce-delays-in-strike-database](chrome://flags/#autofill-enforce-delays-in-strike-database)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Showing Metadata for Virtual Cards

When enabled, Chrome will show metadata together with other card information when the virtual card is presented to users. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-virtual-card-metadata](chrome://flags/#autofill-enable-virtual-card-metadata)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable New Autofill Suggestion Ranking Formula

When enabled, Autofill will use a new ranking formula to rank Autofill data model suggestions such as credit cards or profiles. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-ranking-formula](chrome://flags/#autofill-enable-ranking-formula)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable FIDO Enrollment for Virtual Cards

When enabled, after a successful authentication to autofill a virtual card, the user will be prompted to opt-in to FIDO if the user is not currently opted-in, and if the user is opted-in already and the virtual card is FIDO eligible the user will be prompted to register the virtual card into FIDO. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-virtual-card-fido-enrollment](chrome://flags/#autofill-enable-virtual-card-fido-enrollment)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Autofill Credit Card Upload Save for Select non-Google-based Accounts

When enabled, credit card upload is offered if the user's logged-in account's domain is from a common email provider. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-upstream-allow-additional-email-domains](chrome://flags/#autofill-upstream-allow-additional-email-domains)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Allow Autofill Credit Card Upload Save for All non-Google-based Accounts

When enabled, credit card upload is offered without regard to the user's logged-in account's domain. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-upstream-allow-all-email-domains](chrome://flags/#autofill-upstream-allow-all-email-domains)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Permission Modules on Safety Check

When enabled, adds permission modules to Safety Check on desktop. The modules will be shown depending on the browser state. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#safety-check-permissions](chrome://flags/#safety-check-permissions)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Different UI Variants for the Upload Credit Card Save Bubble

When enabled, it will trigger slightly different UI variants along with notification texts, when the upload credit card save bubble is shown. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#autofill-enable-upstream-save-card-offer-ui-experiment](chrome://flags/#autofill-enable-upstream-save-card-offer-ui-experiment)

                   DefaultEnabledEnabled Faster and ProtectedEnabled Encrypted and SecureEnabled Current with Avatar and EmailDisabled

                 Disabled                 Enabled

## Broker File Operations on Disk Cache in the Network Service

Broker file operations on disk cache running in the Network Service. This is no-op when the Network Service is running in the browser process. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#broker-file-operations-on-disk-cache-in-network-service](chrome://flags/#broker-file-operations-on-disk-cache-in-network-service)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## DMToken Deletion

Delete the corresponding DMToken when a managed browser is deleted in Chrome Browser Cloud Management. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#dm-token-deletion](chrome://flags/#dm-token-deletion)

                   DefaultEnabledEnabled (Forced)Disabled

                 Disabled                 Enabled

## Enable Parsing of the GetDetailsForEnrollResponseDetails in the UploadCardResponseDetails

When enabled, the GetDetailsForEnrollResponseDetails in the UploadCardResponseDetails will be parsed, which will allow the Virtual Card Enrollment flow to skip making a new GetDetailsForEnroll request. This is an optimization to improve the latency of the Virtual Card Enrollment flow. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-get-details-for-enroll-parsing-in-upload-card-response](chrome://flags/#autofill-enable-get-details-for-enroll-parsing-in-upload-card-response)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Quick Intensive Throttling After Loading

For pages that are loaded when backgrounded, activates intensive throttling after 10 seconds instead of the default 5 minutes. Intensive throttling will limit wake ups, from setTimeout and setInterval tasks with a high nesting level and delayed scheduler.postTask tasks, to 1 per minute. See <https://chromestatus.com/feature/5580139453743104> for more info. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#quick-intensive-throttling-after-loading](chrome://flags/#quick-intensive-throttling-after-loading)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## System Color Chooser

Enables a button that launches the macOS native color chooser. – Mac

[#system-color-chooser](chrome://flags/#system-color-chooser)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Ignore Chrome Sync Encryption Keys Long Missing

Drops pending encrypted updates if their key has been missing for a (configurable) number of consecutive GetUpdates. Restarting the browser resets the counter. The threshold is configurable via the MinGuResponsesToIgnoreKey feature parameter. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#ignore-sync-encryption-keys-long-missing](chrome://flags/#ignore-sync-encryption-keys-long-missing)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Parse IBAN Fields in Forms

When enabled, Autofill will attempt to find International Bank Account Number (IBAN) fields when parsing forms. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-parse-iban-fields](chrome://flags/#autofill-parse-iban-fields)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable WebHID on Extension Service Workers

When enabled, WebHID API is available on extension service workers. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-web-hid-on-extension-service-worker](chrome://flags/#enable-web-hid-on-extension-service-worker)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable History Sync Data Type

Enables the History sync data type instead of TypedURLs – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#enable-sync-history-datatype](chrome://flags/#enable-sync-history-datatype)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Biometric Authentication in Settings

Enables biometric authentication in settings to view/edit/copy a password – Mac

[#biometric-authentication-in-settings](chrome://flags/#biometric-authentication-in-settings)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Remade Autofill Downstream Metrics Logging

When enabled, some extra metrics logging for Autofill Downstream will start. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-remade-downstream-metrics](chrome://flags/#autofill-enable-remade-downstream-metrics)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Clipboard Unsanitized Read and Write

Allows reading/writing unsanitized content from/to the clipboard. Currently, it is only applicable to HTML format. See crbug.com/1268679. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#clipboard-unsanitized-content](chrome://flags/#clipboard-unsanitized-content)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable Autofill of IBAN Fields in Forms

When enabled, Autofill will attempt to fill IBAN (International Bank Account Number) fields when data is available. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#autofill-fill-iban-fields](chrome://flags/#autofill-fill-iban-fields)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Parse Standalone CVC Fields for VCN Card on File in Forms

When enabled, Autofill will attempt to find standalone CVC fields for VCN card on file when parsing forms. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-parse-vcn-card-on-file-standalone-cvc-fields](chrome://flags/#autofill-parse-vcn-card-on-file-standalone-cvc-fields)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Batch Fetch Requests

Process resource requests in batches while parsing a HTML document. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#batch-fetch-requests](chrome://flags/#batch-fetch-requests)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop Partial Translate

Enables the Partial Translate feature on Desktop, which allows users to translate text selections on the page through the right click context menu. – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#desktop-partial-translate](chrome://flags/#desktop-partial-translate)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Biometric Authentication Reauth Before Filling

Enables biometric authentication before filling form data – Mac, Windows

[#biometric-authentication-for-filling](chrome://flags/#biometric-authentication-for-filling)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Skip Service Worker Fetch Handler if Skippable

Skips starting the service worker and run the fetch handler if the fetch handler is recognized as skippable. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#skip-service-worker-fetch-handler](chrome://flags/#skip-service-worker-fetch-handler)

                   DefaultEnabledEnabled Not SkipEnabled Skip EmptyDisabled

                 Disabled                 Enabled

## Password Manager New UI

Enables new Password Manager UI on Desktop – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#password-manager-redesign](chrome://flags/#password-manager-redesign)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Desktop PWAs App Home Page

Use new chrome://apps page which has different UX on desktop – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#enable-desktop-pwas-app-home-page](chrome://flags/#enable-desktop-pwas-app-home-page)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable the Battery Saver Mode Feature in the Settings

When enabled, shows the battery section in the performance settings page – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#battery-saver-mode-available](chrome://flags/#battery-saver-mode-available)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Enable the High Efficiency Mode Feature in the Settings

When enabled, shows the performance section in the performance settings page – Mac, Windows, Linux, ChromeOS, Fuchsia, Lacros

[#high-efficiency-mode-available](chrome://flags/#high-efficiency-mode-available)

                   DefaultEnabledEnabled With 5 Second DiscardEnabled With 30 Second DiscardEnabled With 2 Minute DiscardEnabled With 1 Hour DiscardEnabled With Default On and 30 Second DiscardDisabled

                 Disabled                 Enabled

## Enable Merchant Opt-out Error Dialog

When enabled, if the user attempts to use a virtual card on a website where the merchant has opted out of virtual cards, a descriptive error message will appear letting the user know that the merchant has opted out. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#autofill-enable-merchant-opt-out-error-dialog](chrome://flags/#autofill-enable-merchant-opt-out-error-dialog)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Sync Access Handle All Sync Surface

Enables all-sync surface for SyncAccessHandle in File System Access API. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#sync-access-handle-all-sync-surface](chrome://flags/#sync-access-handle-all-sync-surface)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

## Web Authentication Conditional UI

Enable support for Conditional UI WebAuthn requests. – Mac, Windows, Linux, ChromeOS, Android, Fuchsia, Lacros

[#webauthn-conditional-ui](chrome://flags/#webauthn-conditional-ui)

                   DefaultEnabledDisabled

                 Disabled                 Enabled

---
