# Extension Help  #

This wiki will guide you how to use this extension.

For security, only qualified sites can load ActiveX controls on web-pages. In this extension, we manage the qualified sites via rules.

## Quick-help: Auto Configuration ##
Now we support auto-configuration. When it finds ActiveX objects on your webpage, a gray icon will appear on the right of the address bar. Click that icon and choose the corresponding option on the popup page. Refresh the page. A green icon will indicate the ActiveX controls are working. [More information on Icons](#Icons.md)

If the icon is not displayed, you can active it manually on the option page. On that page, you can select some predefined rules you're interested in. Click the button before the rule to toggle it, or create your own.

Just that easy! If you like this extension, please share it to your friends and [rate it Five Stars](https://chrome.google.com/webstore/detail/lgllffgicojgllpmdbemgglaponefajn)!  If you can afford to, donte us as you wish. Open the donation page from the options page of the extension.

## Advanced: Manual config ##

The option page is where you can manipulate the rules. You can either enable predefined rules or create your own ones. To enable or disable a predefined rule, just click on the button before its name. Click "Add" to create custom rules. **We strongly recommend you to use predefined rules if possible.** Predefined rules are updated automatically or by clicking `Update now` on options page.

Once an ActiveX control matches one of the rules, it will be activated automatically on web-pages. We have 3 modes in matching rules:
  1. WildChar
  1. RegExp
  1. CLSID
### WildChar ###
Just like windows-search, we use `*` to represent any number of chars. If the URL of the page matches the pattern, all controls on the page will be enabled. So `http://*.google.com/*` will match `https://www.google.com/chrome/eula.html?extra=betachannel`. However, some restrictions are made in case some malicious sites hack.

It must have the format like `scheme://site/path`. Scheme can be http, file, https, or `*` to present any one. Site can start with `*`, but it can't have any `*` in the middle or tail. So pattern like `http://*.google.*/*` is incorrect. The path can  be any string or empty, but the slash between site and path **cannot** be omitted.
### RegExp ###
We also support Regular Expression to construct complicated patterns. It's equivalent to JavaScript RegExp. The entire URL must matches the pattern to be qualified.
### CLSID ###
CLSID mode matches controls by its CLSID. It's useful for the controls that are used on different sites. For example, a CLSID rule with value `22D6F312-B0F6-11D0-94AB-0080C74C7E95` will enable all controls of Windows Media Player. You must include the hyphen `-` in CLSID. In this mode, UserAgnet and HelperScript are not supported.

## User Agent ##
In case the features of ActiveX controls are disabled by the site if you're not using IE, you can mock your browser through setting UserAgent in the rules  matched by URL (WildChar or RegExp). Typically, set UserAgent to IE9 will be adequate. However, we recommend you to set UserAgent other than Chrome only if it's demanded, or it will slow down your browser's interaction.

## Helper Script ##
Because some sites, especially ones with ActiveX controls, are not well written and browser-compatible, we need some other scripts to make them work. If the rule is matched via URL (WildChar or RegExp), you can associate additional helper scripts with the rule. These scripts will be executed automatically when a page with matched URLs are loaded. Use space to separate more than one scripts.
Here are some most useful helper scripts:
  * **ieevent**      Allow to use `attachEvent` and `detachEvent` on DOM elements.
  * **dynamic**      Allow to create ActiveX objects with JavaScript(`new ActiveXObject()`)
  * **none2block**   Can load hidden ActiveX objects. See [issue 7](https://code.google.com/p/np-activex/issues/detail?id=7) for detail.
  * **ieidname**     `document.getElementById` will also return element by name.
Now we don't support custom helper script. You can file an issue to us on new helper scripts.

## Icons ##
When the page you're viewing contains ActiveX controls, an icon will appear at the right of address bar. The color of the icon will indicate the status of the controls.

Green**All of the ActiveX controls are working. You can report problem by clicking it.** **Gray** The controls are not active. You can enable them immediately by clicking the icon and select the corresponding action.
Red**We have found some errors which make the controls not working. We'll fix the problem later. We feel sorry for that.**

### Why I can't find the icon? ###
If you cannot find the icon at the address bar, it may be because:
**The page you're visiting doesn't have any ActiveX controls at all.** The page is open in a popup window, which doesn't allow any icon to be displayed at the right of the adderss bar. Please paste the URL to another tab and open it.
**The page detects your browser and decides whether to load the controls. In that case, you must activate it manually on the option page, and set the UserAgent to IE.**

## Feedback ##
If some sites can't be used or you have some suggestions, please tell us. Click [here](http://code.google.com/p/np-activex/issues/list) to open the issue report page, but we recommend you to send issues with the extension.

Click the icon at the right of the address bar, you can find a button _Report problem_. Click that button, and continue operating that page. When the page is closed, a guide will popup to tell you how to submit issue.

If you can't find the icon, it may because the site doesn't uses ActiveX controls at all, or it's disabled by the site because UserAgent is not set to IE. Adjust your configuration properly. You can also open the logging page manually from the options page. Please be noted that the logs are cleared automatically unless the "tracking" option is ticked.

If the icon has a red cross, we have already acknowledged that problem. Please don't resubmit.