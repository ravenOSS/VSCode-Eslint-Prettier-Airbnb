# VSCode - ESLint, Prettier & Airbnb Setup

The recommendation is to install packages on a per project basis except for ESLint & Prettier which are installed globally.<br>

This ensures that anyone cloning a repository with the given settings will not run into conflicts with their own configurations.<br>

Objective is to not overlap linting (code syntax) with formatting.<br>
Prettier is the formatting tool and Airbnb provides a ruleset.<br>

Two local config files are required in project root: .eslintrc.json and .prettierrc.<br>

Tune the configurations to your needs by reviewing package information.

### 1. Install ESLint & Prettier from extensions panel in VSCode<br>

These will be installed globally

### 2. Configure VSCode

- There are some options provided in the VSCode settings.json.
- Set format on save and any global prettier options.
- Ensure that eslint is not selected as the code formatter.

### 3. Install Packages

```
npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-node eslint-config-node
```

Note that the following uses npx

```
npx install-peerdeps --dev eslint-config-airbnb
```

### 4. Create .prettierrc for any prettier rules (semicolons, quotes, etc)

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "semi": false,
  "singleQuote": true,
  "jsxSingleQuote": true,
  "trailingComma": "es5",
  "bracketSpacing": true,
  "jsxBracketSameLine": false,
  "arrowParens": "always"
}
```

### 5. Create .eslintrc.json file (You can generate with eslint --init if you install eslint globally)

```json
{
  "extends": [
    "airbnb",
    "prettier",
    "plugin:node/recommended",
    "eslint:recommended",
    "plugin:node/recommended"
  ],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error",
    "no-unused-vars": "warn",
    "no-console": "off",
    "func-names": "off",
    "no-process-exit": "off",
    "object-shorthand": "off",
    "class-methods-use-this": "off"
  }
}
```

- TODO Review eslint settings in vscode settings.json
- TODO Include Babel config
- TODO Review node plugin config (engines?)
- TODO Review eslint-config-node config
- TODO Normalize config files to readme content

## ALTERNATIVES

- This repo provides a command line script that builds a configuration in a project folder.<br>
  Script source:<br>
  https://github.com/paulolramos/eslint-prettier-airbnb-react

- Blogpost:
  https://dev.to/bigyank/a-quick-guide-to-setup-eslint-with-airbnb-and-prettier-3di2

### Reference

- ESLint Rules - https://eslint.org/docs/rules/
- Prettier Options - https://prettier.io/docs/en/options.html
- Airbnb Style Guide - https://github.com/airbnb/javascript
