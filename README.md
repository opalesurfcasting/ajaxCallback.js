# ajaxCallback.js - SPIP 3.1.x and above
Canonicalize SPIP javascript prive/javascript/ajaxCallback.js
using [jsDelivr Github CDN](https://www.jsdelivr.com/feature) and [mod_pagespeed](https://www.modpagespeed.com/doc/filter-canonicalize-js).

## In Apache pagespeed.conf:

This will enable canonicalization for ajaxCallback.js (SPIP 3.1.x) using [jsDelivr Github CDN](https://www.jsdelivr.com/feature) - The parameter below will enable detection from this librarie size and checksum :
 ```
 ModPagespeedEnableFilters canonicalize_javascript_libraries
 ```
 Adding this  :
 ```
 ModPagespeedLibrary 21074 NvlVPCOPnd86d229dLuoo \
 //cdn.jsdelivr.net/gh/opalesurfcasting/ajaxCallback.js@v1.0/ajaxCallback.min.js
 ```
 will enable canonicalization for ajaxCallback.js, also based on file size 21074 and checksum. This is needed as this file is not in default mod_pagespeed [canonicalized libraries list](https://github.com/pagespeed/mod_pagespeed/blob/master/net/instaweb/genfiles/conf/pagespeed_libraries.conf).
 
 ## Find the size and checksum :
 
 `pagespeed_js_minify --print_size_and_hash library.js` - [Find the size and checksum](https://www.modpagespeed.com/doc/filter-canonicalize-js)
 
## Direct urls :
 
 using opalesurfcasting Github repository :
 
 raw : https://cdn.jsdelivr.net/gh/opalesurfcasting/ajaxCallback.js@v1.0/ajaxCallback.js
 
 minified : https://cdn.jsdelivr.net/gh/opalesurfcasting/ajaxCallback.js@v1.0/ajaxCallback.min.js
 
 using Spip Github repository (better, maybe more users) :
 
 raw : https://cdn.jsdelivr.net/gh/opalesurfcasting/ajaxCallback.js@v1.0/ajaxCallback.js
 
 minified : https://cdn.jsdelivr.net/gh/opalesurfcasting/ajaxCallback.js@v1.0/ajaxCallback.min.js
 
 ## Notes :
 
 - When canonicalized, libraries will not be combined or minifyed by mod_pagespeed, but it can be done through [jsdlivr](https://www.jsdelivr.com/?docs=gh). It's up to you to check what is the best.
