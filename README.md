# .npm_global
My "globally"-installed npm packages.

## Usage
The purpose of this package is to provide "globally" installed modules (i.e.
command line tools) be managed like a regular package with locally-installed
modules. This simplifies some processes, at the relatively low cost of adding a
directory to the `$PATH`.

### Recommended install method
1. Clone the repo to your home directory.
2. Install the modules: `npm install`
3. Add the following to your `.profile`, `.bash_profile`, etc.:
```sh
# set PATH so it includes custom globally-installed node modules
if [ -d "$HOME/.npm_global/node_modules/.bin" ] ; then
    PATH="$HOME/.npm_global/node_modules/.bin:$PATH"
fi
```

### Adding a new global package
Use `cd ~/.npm_global && npm install --save-dev <package>` to install a new
package and save it as a `devDependency` (recommended, since command line tools
are generally part of a development workflow anyway).

For convenience, an alias can be created:
```sh
# work with npm in ~/.npm_globals
alias npm_g='cd ~/.npm_global && npm'
```

For example, this lets you use `npm_g install --save-dev <package>` to install
and save a new dependency.

