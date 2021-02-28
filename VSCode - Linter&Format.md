# VSCode - ESLint, Prettier & Airbnb Setup
The recommendation is to install packages on a per project basis except for ESLint & Prettier.<br>

This ensures that anyone using the repository will not run into   
conflicts with their own configurations.<br>

Objective is to not overlap linting (code syntax) with formatting.<br>
Prettier is the formatting tool and Airbnb provides a ruleset.<br>

Two local config files are required .eslintrc.json and .prettierrc.<br>

### 1. Install ESLint & Prettier from extensions panel in VSCode<br>
These will be installed globally

### 2. Configure VSCode
Open Optional - Set format on save and any global prettier options

### 3. Install Packages
```
npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-node eslint-config-node
```

```
npx install-peerdeps --dev eslint-config-airbnb
```

### 4. Create .prettierrc for any prettier rules (semicolons, quotes, etc)

### 5. Create .eslintrc.json file (You can generate with eslint --init if you install eslint globally)

```json
{
  "extends": ["airbnb", "prettier", "plugin:node/recommended"],
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
## ALTERNATIVE
Script source:<br>
https://github.com/paulolramos/eslint-prettier-airbnb-react


### Reference
* ESLint Rules - https://eslint.org/docs/rules/
* Prettier Options - https://prettier.io/docs/en/options.html
* Airbnb Style Guide - https://github.com/airbnb/javascript