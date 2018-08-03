# Example Prettier Project

* Demonstrates Prettier with .prettierrc to format JS, JSX, **and Vue** (though, to be fair, version 3 of the Vue CLI _may_ render this branch unnecessary)
* Uses Husky and lint-staged to automatically lint and apply fixes as a pre-commit hook


## Code Branches

* [master](https://github.com/nullfame/hello-prettier/tree/master): code from the develop branch marked as a release
* [develop](https://github.com/nullfame/hello-prettier/tree/develop): primary branch containing the basic setup
  * [framework/vue](https://github.com/nullfame/hello-prettier/tree/framework/vue): branch of develop with Vue-specific configuration


## Setup and Usage

* Run `npm install`
* Any time you commit changes, ESLint will automatically apply Prettier's fixes.  If this fails (i.e., there is an "error" it cannot automatically fix) the commit will fail until a fix is manually applied.  Use `git commit --no-verify` if you have a good reason to commit without fixing an error and make it the next person's problem
* `npm run lint` will display a list of errors from both the airbnb-base (i.e., all their non-React rules) and Prettier rulesets but will NOT apply fixes
* `npm run format` will automatically fix all the errors it can (formatting and many recommendations), save those changes to disk, and display errors and warnings it cannot fix


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


## Notes

* `format` and `lint` npm commands manually specify `exit 0` to not generate an NPM error when eslint exits with a code other than zero (because it detected an error in your code).  This is NOT done in the precommit hook because eslint exiting with an error is desired to prevent the commit
* I was formatting JSON but decided that was too much.  Maybe with a ruleset specific to JSON
* HTML formatting in VSCode isn't working at the moment.  Not entirely sure why that's the case.  Vetur's HTML formatter is currently disabled by default as it is "not actively maintained and has many long-standing bugs" so "will be removed soon."  Formatting on commit still works which leads me to believe I should be able to get this working in VSCode, I just can't.


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
