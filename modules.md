# Modules, Themes and Libraries

Run the following command to ensure all required modules and themes are installed.

In development, prefix command with `ddev`. The `-n` options prevents redownloading modules that are already present.

```bash
drush dl -n admin_menu adminimal_theme advanced_help backup_migrate \
better_exposed_filters breakpoints captcha ctools entity entityreference \
eu_cookie_compliance expire fast_token_browser fb_likebox file_entity \
geofield geophp globalredirect honeypot imagecache_token jquery_update \
leaflet libraries media metatag module_filter nodeorder oauth pathauto \
picture recaptcha schema_metatag security_review smtp superfish token \
token_filter transliteration twitter user_picture_field views xmlsitemap
```

Leaflet requires patching to correctly detect the version.

```bash
cd sites/all/modules/leaflet
curl https://www.drupal.org/files/issues/2018-11-29/leaflet-version-check-2895968-39_0.patch | patch -p1
```

## Libraries



```bash
cd ../../libraries

# install leaflet.js
wget -L https://leafletjs-cdn.s3.amazonaws.com/content/leaflet/v1.9.3/leaflet.zip
unzip leaflet -d leaflet
rm leaflet.zip

# install superfish.js
wget -L https://github.com/mehrpadin/Superfish-for-Drupal/archive/1.x.zip
unzip 1.x -d superfish
rm 1.x.zip

# install jQuery easing
mkdir easing
wget https://github.com/gdsmith/jquery.easing/blob/master/jquery.easing.min.js -O easing/jquery.easing.js
```
