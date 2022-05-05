# OWASP ModSecurity Core Rule Set - DokuWiki Rule Exclusions Plugin

## Description

This plugin contains rule exclusions for [DokuWiki](https://www.dokuwiki.org), simple and versatile wiki software that doesn't require a database. These rule exclusions are designed to resolve common false positives and allow for easier integration with the OWASP ModSecurity Core Rule Set (CRS).

## Installation

For full and up to date instructions for the different available plugin installation methods, refer to [How to Install a Plugin](https://coreruleset.org/docs/concepts/plugins/#how-to-install-a-plugin) in the official CRS documentation.

## Testing

After the plugin is enabled, DokuWiki should work without problems caused by CRS (for example, false positives while blocking requests). If problems still occur then please file a new issue on [GitHub](https://github.com/coreruleset/dokuwiki-rule-exclusions-plugin). (Note that high paranoia level deployments may require additional tuning beyond this plugin.)

## License

Copyright (c) 2022 OWASP ModSecurity Core Rule Set project. All rights reserved.

The OWASP ModSecurity Core Rule Set and its official plugins are distributed under Apache Software License (ASL) version 2. Please see the enclosed LICENSE file for full details.
