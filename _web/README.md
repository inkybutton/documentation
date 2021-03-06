OpenCMISS Website
=================

Source for the new OpenCMISS website.
License TBD.

Dependencies
------------
* Python 2.7.
* nodejs
* npm
* bower (installed through npm)
* grunt-cli (installed through npm)
* virtualenv
* (Optional) make

The project also depends on packages from npm, bower and pip.

Building the website
--------------------
1. Install the dependencies from your system's packaging manager. For example, in Debian jessie:

   ```
   sudo apt-get install git python nodejs npm virtualenv make
   sudo npm -g install bower
   sudo npm -g install grunt-cli
   ```

   In the future a Guix package script may be provided to take care of the installation.

2. Clone this repository.

3. Enter the `_web` directory, install npm and bower packages and do a build:

   If you have make simply run the following. Replace [URL] with the root of where this site will be hosted, e.g. "next.opencmiss.org". This is used for generating a sitemap for the website. 

   ```
   cd _web
   export SITE_URL=[URL];make
   ```

   Otherwise, run:

   ```
   cd _web
   virtualenv .pythonenv
   .pythonenv/bin/pip install -r requirements.txt
   npm install
   bower install
   grunt
   ```


4. The built website is now available in `_web/build/dist/`. Serve with your favourite web server.
