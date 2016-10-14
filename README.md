# NVM

* nvm ls-remote -> lists all the available versions
* nvm install [vNumber] -> self explanatory
* nvm use [vNumber] -> switches to selected version

# NPM

* curl http://npmjs.org/install.sh | sh -> npm install/ update
* npm view [pkgName] -> shows pkg details
* npm install [pkgName] -> installs a pkg locally
* npm install [pkgName] -g -> installs a pkg globally
* npm uninstall [pkgName] [-g] -> self explanatory [globally]
* to use a module in a script insert this at the top -> var [moduleName] = require('[moduleName]');

# ESLint

* Create '.eslintrc.json' file
* Add airbnb:
* globally -> run 'npm install -g eslint-config-airbnb eslint-plugin-import eslint-plugin-react eslint-plugin-jsx-a11y'

# Ruby

Testing Environment:
* install ruby testing framework -> run 'gem install rspec'
* include name of the file in the tests -> 'require('./[testedFile].rb')'
* run tests on the file run 'rspec [-fd] [tests].rb'
