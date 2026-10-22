# OWASP CRS - DokuWiki Rule Exclusions Plugin

## Description

This plugin contains rule exclusions for [DokuWiki](https://www.dokuwiki.org), simple and versatile wiki software that doesn't require a database. These rule exclusions are designed to resolve common false positives and allow for easier integration with the OWASP CRS (CRS).

## Installation

For full and up to date instructions for the different available plugin installation methods, refer to [How to Install a Plugin](https://coreruleset.org/docs/concepts/plugins/#how-to-install-a-plugin) in the official CRS documentation.

### Conditionally enable plugins for multi-application environments

For full and up to date instructions on how to conditionally enable/disable this plugin on a multisite environment, please refer to [Conditionally enable plugins for multi-application environments](https://coreruleset.org/docs/concepts/plugins/#conditionally-enable-plugins-for-multi-application-environments) in the official CRS documentation.

## Testing

After the plugin is enabled, DokuWiki should work without problems caused by CRS (for example, false positives while blocking requests). If problems still occur then please file a new issue on [GitHub](https://github.com/coreruleset/dokuwiki-rule-exclusions-plugin). (Note that high paranoia level deployments may require additional tuning beyond this plugin.)

## Coraza/CrowdSec AppSec default body processor
By default, Coraza (used by CrowdSec AppSec) will use the URLENCODED body processor when no other request body processor has been configured. Which body processor Coraza uses is defined in the coraza.conf file. The default behavior is not desirable for Dokuwiki due to it supporting file upload. The following rule can be used to enable the RAW body processor when no other parser has been configured.

```
SecRule REQBODY_PROCESSOR "!@rx (?:URLENCODED|MULTIPART|XML|JSON)" \
    "id:9509030,\
    phase:1,\
    pass,\
    nolog,\
    ctl:requestBodyProcessor=RAW"
```

**NOTE:** tx.enforce_bodyproc_urlencoded is effectively the same thing as described above, tx.enforce_bodyproc_urlencoded is supported by this plugin and contains rule-exclusions to handle false positives resulting from forcing a body processsor.

## License

Copyright (c) 2022 OWASP CRS project. All rights reserved.

The OWASP CRS and its official plugins are distributed under Apache Software License (ASL) version 2. Please see the enclosed LICENSE file for full details.
