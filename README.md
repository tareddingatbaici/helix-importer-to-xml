This contains modified code from
* https://github.com/adobe/helix-importer-ui
* https://github.com/adobe/helix-importer
* https://www.npmjs.com/package/@adobe/helix-md2docx

It adds functionality to convert to xml instead of just html, docx, and md.
The end goal of this project is to allow the importer tool to scrape website content and convert it directly to an aem content package.
See the other repos for more documentaton.

To run the helix-importer ui with modified changes and also not making our own version of the aem helix cli, there are some hacky workarounds I am using that will be detailed below.

How to build/run:
1. Install the aem cli with "npm install -g @adobe/aem-cli"
2. Change tools/importer/helix-importer-ui/CHANGETHISTO.git to tools/importer/helix-importer-ui/.git (This is so the "aem import" command doesn't get confused and throw the "Could not find HEAD." error, but our modified code isn't treated as a git submodule so it properly commits changes to this repo)
3. Delete tools/importer/helix-importer-ui/js/dist ("aem import" will attempt to override this and get confused the first time it's ran otherwise)
4. In the root directory (It MUST be in the root directory or the aem import tool will make a new copy of the helix-importer-ui under tools/importer/) Run "aem import" and then close it (Ctrl + C in cli)
5. In root directory, run "cd helix-md2xml/ && npm install && cd ../helix-importer/ && npm install && cd ../helix-importer-ui/ && npm run build:dev && cd ../". This is a hacky solution, if one of the steps fails then the rest won't run. This will add back in our changes to helix-importer-ui
6. In the root directory (!IMPORTANT!), run "aem import". If this was done correctly, the ui should show the option "Save as Xml"

You may need to redo steps 3-6 each time you restart your machine.

How to run:
* In root directory (Important! Run this in root dir or else the aem cli will downoad a clean copy of helix-importer-ui under whatever dir you're in) run "aem import"
