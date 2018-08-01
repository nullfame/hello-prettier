# Example Prettier Project

* Demonstrates Prettier with .prettierrc to format JS, JSX, JSON, **and Vue** (though, to be fair, version 3 of the Vue CLI _may_ render this branch unnecessary)
* Uses Husky and lint-staged to automatically lint and apply fixes as a pre-commit hook


## Code Branches

* [master](https://github.com/nullfame/hello-prettier/tree/master): code from the develop branch marked as a release
* [develop](https://github.com/nullfame/hello-prettier/tree/develop): primary branch containing the basic setup
  * [framework/vue](https://github.com/nullfame/hello-prettier/tree/framework/vue): branch of develop with Vue-specific configuration


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
        "javascript",
        "vue"
    ]
}
```

This will apply as many fixes as possible on save events.  Add `"files.autoSave": "onWindowChange"` for even more excitement.


## References 

Most of this was inspired by this post by Christopher Hamilton:<br>
<https://www.39digits.com/configure-prettier-and-eslint-in-visual-studio-code/>

He covers formatting on a pre-commit hook here:<br>
<https://www.39digits.com/automatically-format-your-javascript-commits-using-prettier-and-husky/>

The only exception is my decision to NOT install the Prettier plugin for VSCode, which was inspired by Wes Bos:<br>
<https://www.youtube.com/watch?v=YIvjKId9m2c>

Sebastian Weber wrote a Medium article about ESLint and Prettier with Vue:<br>
<https://medium.com/@doppelmutzi/eslint-prettier-vue-workflow-46a3cf54332f>


## License

&copy; Northwestern University.  All rights reserved.

Any unauthorized use of this package 
without the express written consent of Morty Schapiro 
is strictly prohibited.
