# Run project locally

* Check `package.json` to rebuild (ensure that you take a look at the dependencies that need to be installed)

* Checkpoints: 1) `yarn install`, 2) `npm run build:css`, 3) `npm start` 🚀

* If you get an error: `npm install -g node-sass`, then run: `npm-run-all compile:sass prefix:css compress:css`

-----

**Scenario 1**: more than one error persists, we may have to regenerate the `package.json` file, so delete it, and the `node_modules` too and then use `npm init` in the command line.

**Scenario 2**: Sometimes it has to do with `sudo` and `npm` unable to communicate. Here's a set of commands I ran to fix it. Link [here](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)).

```
sudo npm install -g npm
npm audit fix --force
yarn install
npm run build:css
npm install live-server
npm install -g node-sass
sudo npm install -g node-sass
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
export PATH=~/.npm-global/bin:$PATH
source ~/.profile
npm install -g jshint
NPM_CONFIG_PREFIX=~/.npm-global
npm install -g node-sass
npm-run-all compile:sass prefix:css compress:css
npm start
```