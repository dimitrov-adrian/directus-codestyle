# unofficial Directus Codestyle

A sharable Directus codestyle configuration.

> Exported from Directus main repository https://github.com/directus/directus

> Sort of continuation of https://github.com/directus/directus/pull/8586

## Includes

- eslint config
- stylelint config
- prettier config

## Install

```
npm install --save-dev dimitrov-adrian/directus-codestyle
```

## Usage

### Own config files

Use regular configuration files for eslint, stylelint and prettier.

```js
// .prettierrc.js
module.exports = {
	...require('directus-codestyle/prettier'),
	// your overrides here
};
```

```js
// .eslintrc.js
module.exports = {
	...require('directus-codestyle/eslint'),
	// your overrides here
};
```

```jsonc
// .stylelintrc.json
{
	"extends": ["directus-codestyle/stylelint"]
	// your overrides here
}
```

### or Package.json

```jsonc
// package.json
{
	"prettier": "directus-codestyle/prettier",
	"stylelint": {
		"extends": "directus-codestyle/stylelint"
	},
	"eslintConfig": {
		// Because of way how eslint normalize config module names, need to use absolute.
		"extends": "./node_modules/directus-codestyle/.eslintrc.js",
		"parserOptions": {
			"sourceType": "module"
		}
	}
}
```

## Editor Integration

### VS Code

- Prettier - Code formatter
- ESLint
- Stylelint
- Vetur
- (optional) EditorConfig for VS Code
- (optional) Vue
- (optional) VueDX

##### Simple vscode settings

```jsonc
{
	"stylelint.validate": ["css", "less", "postcss", "vue"],
	"[javascript]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[typescript]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[vue]": {
		"editor.defaultFormatter": "octref.vetur"
	},
	"[json]": {
		"editor.defaultFormatter": "vscode.json-language-features"
	}
}
```
