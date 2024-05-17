This contains modified code from
* https://github.com/adobe/helix-importer-ui
* https://github.com/adobe/helix-importer
* https://www.npmjs.com/package/@adobe/helix-md2docx

It adds functionality to convert to xml instead of just html, docx, and md.
The end goal of this project is to allow the importer tool to scrape website content and convert it directly to an aem content package.
See the other repos for more documentaton.

How to build:
* Install the aem cli with "npm install -g @adobe/aem-cli"
* In root directory, run "cd helix-md2xml/ && npm install && cd ../helix-importer/ && npm install && cd ../helix-importer-ui/ && npm run build:dev && cd ../"

How to run:
* In root directory (Important! Run this in root dir or else the aem cli will downoad a clean copy of helix-importer-ui under whatever dir you're in) run "aem import"
