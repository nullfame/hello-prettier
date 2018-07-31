# Example Prettier Project

* Demonstrates Prettier with .prettierrc to format JS,JSX,JSON
* Uses Husky and lint-staged to automatically lint and apply fixes as a pre-commit hook


## Setup and Usage

* Run `npm install`
* Any time you commit changes, ESLint will automatically apply Prettier's fixes
* `npm run lint` will display a list of errors (but not warnings) from both the airbnb-base (i.e., all their non-React rules) and Prettier rulesets but will NOT apply fixes


## Configuring VSCode (optional)

One of many possible ways to configure VSCode is to install the ESLint extension by Dirk Baeumer but NOT the Prettier extension and include the following in your user settings:

```javascript
{
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": false,
    },
    "eslint.alwaysShowStatus": true,
    "eslint.autoFixOnSave": true,
    "eslint.validate": [
        "javascript"
    ]
}
```

This will apply as many fixes as possible on save events.  Add `"files.autoSave": "onWindowChange"` for even more excitement.


## License

&copy; Northwestern University.  All rights reserved.

Any unauthorized use of this package 
without the express written consent of Morty Schapiro 
is strictly prohibited.
