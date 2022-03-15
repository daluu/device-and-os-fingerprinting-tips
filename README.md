# Tips on device fingerprinting

Notes on where to get device fingerprint mappings.

## Mac and iOS devices

Start from https://github.com/SeparateRecords/apple_device_identifiers, 
viewing the data there, and the referenced links to other resources.

## Android devices

Maybe check here: https://support.google.com/googleplay/answer/1727131?hl=en, particularly https://storage.googleapis.com/play_public/supported_devices.html.

## Amazon devices

* https://developer.amazon.com/docs/fire-tablets/ft-identifying-tablet-devices.html
* https://developer.amazon.com/docs/fire-tablets/ft-user-agent-strings.html
* https://developer.amazon.com/docs/fire-tv/identify-amazon-fire-tv-devices.html
* https://developer.amazon.com/docs/fire-tv/user-agent-strings.html
* https://whatismyphone.net/vendors/amazon?page=2

## Smart TV devices

* https://deviceatlas.com/blog/list-smart-tv-user-agent-strings

## Chromebook/Chrome OS devices

Maybe check here: https://support.google.com/googleplay/answer/1727131?hl=en, particularly https://sites.google.com/a/chromium.org/dev/chromium-os/chrome-os-systems-supporting-android-apps

## Device browser databases

* https://whatismyphone.net/vendors/amazon?page=2
* https://deviceatlas.com/device-data/devices/samsung
* http://www.tera-wurfl.com/explore/search.php?action=browse

## In general

* https://deviceatlas.com/blog/list-of-user-agent-strings

Occasionally online search for user agent strings of device/model/OS of interest and see what the user agent 
monitoring/repository websites (e.g. http://whatismybrowser.com , http://useragentstring.com, etc.) present. 
Sometimes you come across info on reddit, github, StackOverflow, and public issue/bug reports, e.g:

* https://www.reddit.com/r/GamingLeaksAndRumours/comments/j620vi/user_agent_strings_of_playstation_5/ 
* [Xbox 360 Internet Explorer (ie) User Agent](https://gist.github.com/tony4d/3916185)
* [Detecting Chromecast through Javascript](https://issuetracker.google.com/issues/36189456)

## Not so common user agent strings

As browsers on Mac (and Windows) stopped reporting OS version in recent OS versions, you can only rely on client hints to get at the OS information, in supported browsers. Refer to these for info:

* https://web.dev/user-agent-client-hints/
* https://browserleaks.com/client-hints
* https://docs.microsoft.com/en-us/microsoft-edge/web-platform/how-to-detect-win11

* https://www.chromestatus.com/feature/5080939765956608
* https://bugzilla.mozilla.org/show_bug.cgi?id=1693295
* https://bugzilla.mozilla.org/show_bug.cgi?id=1679929
* https://bugs.webkit.org/show_bug.cgi?id=216593
* https://trac.webkit.org/changeset/267148/webkit
* https://groups.google.com/u/1/a/chromium.org/g/blink-dev/c/hAI4QoX6rEo/m/qQNPThr0AAAJ

aside from that, you may be able to find additional info from HTTP headers sent by non-browser applications/services...(the following below won't help if you're focused strictly on web (browser) and mobile web-view based applications endpoints).

### For Windows

The following types of (non-browser) user agents (or parts of user agent or user agent related fields) can be used to refer to specific range of Windows versions or generically a Windows OS. You can internet search the terms below for some more insight. These values are only applicable if you sniff the HTTP headers, etc. content from the network side, less likely so analyzing it from the browser client side (developer tools, etc.), web server (logs) side, etc. since these are non-browser values. They are passed along from native OS level (background) services or from mobile/desktop apps.

#### Windows 10 (and above, e.g. Windows 11)

* Microsoft-CryptoAPI/10.0
* Microsoft-Delivery-Optimization/10.0
* Microsoft-WNS/10.0
* Windows-Update-Agent/10.0

#### Generic Windows OS

* MSIE
* MSIPC
* .NET CLR
* .NET4
* OSName=Windows
* Windows NT
* Windows-Media-Player
* Windows-RSS-Platform
* WinHttpClient
* WinHttp-Autoproxy-Service
* WINWORD.EXE
* Microsoft
* IE

### For Miscellaneous Apple Stuff

The following types of (non-browser) user agents (or parts of user agent or user agent related fields) can be used to refer to generically, some Apple OS and device. You can internet search the terms below for some more insight. These values are only applicable if you sniff the HTTP headers, etc. content from the network side, less likely so analyzing it from the browser client side (developer tools, etc.), web server (logs) side, etc. since these are non-browser values. They are passed along from native OS level (background) services or from mobile/desktop apps.

#### Generic iOS (the OS itself as well as generic iOS device)

* CaptiveNetworkSupport
* itunesstored

#### Generic Apple Mac OS (and generic Apple Mac device)

* com.apple
* Darwin
* CFNetwork
* server-bag
* trustd
* securityd
* AppleCoreMedia

#### Mac OS versions from non-browser user agent info (prefixes/parts, etc.)

* `[macOS,12` = Monterey
* `[macOS,11` = Big Sur
* Mac OS X 11 = Big Sur
* Intel Mac OS X 11_0_0 = Big Sur
* Intel Mac OS X 10.16 = Big Sur
