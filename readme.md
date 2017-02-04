# Errorpage customization for Apache HTTP server
This package configures your Apache HTTP server to use custom error pages instead of the default ones (with old and invalid HTML markup).

## Dependencies
This customization requires that your Apache HTTP server is equal to or greater than **2.4** in the version. In addition, the following modules needs to be enabled:

* `mod_alias`: <https://httpd.apache.org/docs/2.4/mod/mod_alias.html>
* `mod_include`: <https://httpd.apache.org/docs/2.4/mod/mod_include.html>
* `mod_authz_core`: <https://httpd.apache.org/docs/2.4/mod/mod_authz_core.html>

## SSI variables
The following variables are defined within each `xxx.shtml` file within the `customization/errorpage/` directory:

* `ERRORPAGE_CODE`: This variable contains the HTTP status code for the current error or information page.
* `ERRORPAGE_TEXT`: This variable contains the description of the HTTP status code defined with `ERRORPAGE_CODE`.
* `ERRORPAGE_INFO`: This variable contains an additional and *meaningful* description for the user about the current page.

## Installation
All files and directories provided in this package are relative to the `/etc/apache2/` (depends on the system you use) directory. To activate the configuration, just execute `a2enconf errorpage` and reload the configuration with `systemctl reload apache2`.