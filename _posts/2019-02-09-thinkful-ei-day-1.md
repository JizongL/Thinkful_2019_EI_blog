---
layout: post
title: Thinkful EI Study note day 1
date: 2019-02-09 17:32
categories: Thinkful 
tags: EI_program local_dev_environment
---

* content
{: toc}


## Local Dev environment setup(MAC)

Visual Studio Code

download and install Visual studio Code
`Open the Command Palette (⇧ ⌘ P)` and type `shell command`
Open terminal and test run `code ~/Desktop`

Homebrew
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Git
[sign up for GitHub](https://github.com/join?source=header-home)
`brew install git`
`git --version` confirm version

*Configuration*

Now from the same Terminal window, run `git config --global user.name "Sally Student"` (substituting your user name), and then `git config --global user.email "sallystudent2017@gmail.com"` (substituting your email address).


Node and NPM
`brew install node`
`node --version and npm --version`

test node install

`mkdir hello_node && cd hello_node`
`echo "console.log("hello world")" > hello.js`
`cat hello.js` confirm file created properly. 
`node hello.js`

[Express generator](https://www.npmjs.com/package/express-generator)
`npm install -g express-generator` install globally 
`express hello_express` test create a new app
`cd hello_express` and `npm install` install dependencies listed in `package.json`
`npm start`
`localhost:3000` to visit new app and shall see "Welcome to express".


Installing ESLint
compared to JLint, JHint, ESLint is most popular and customizable 

function 
static analysis to find syntax errors, and problematic code before you run the code

installed globally 
`npm install -g eslint`
And configuration file is placed in your root directory so it will run across all projects. 

installed locally 
`--save-dev` option like npm install `eslint --save-dev` so an entry is placed in the devDependencies property in package.json. And a configuration file is placed in the root of the project which overrides the global configuration and allows for project specific configuration.

`cd ~/`
`.eslintrc.json`

paste the following into the json file 

```js
{
    /** 
    * ESLint: http://eslint.org/docs/user-guide/configuring
    */

    // "env:" supplies predefined global variables
    "env": {
        "browser": true,
        "es6": true,
        "node": true,
        "mocha": true,
        "mongo": true
    },
    // our configuration extends the recommended base configuration
    "extends": "eslint:recommended",
    // define the type of file `script` or `module` for ES6 Modules
    "parserOptions": {
        "sourceType": "script"
    },
    //ESLint rules: Severity Levels: off = 0 | warn = 1 | error = 2
    "rules": {
        "strict": ["error", "safe"],   //prefer `'use-strict';` pragma
        "eqeqeq":"error",              //prefer strict equality `===`
        "no-console": "warn",          //allows but warn about console like `console.log()`
        "no-unused-vars": "warn",      //warns about unused variables
        "no-eval": "error",            //disallows `eval()` usage
        "indent": ["error", 2],        //enforce 2 space indents (not tabs)        
        "quotes": ["error", "single"], //prefer single quotes over double quotes
        "semi": ["error", "always"]    //enforce semi-colon usage
    }
}
```

read more about on [Specifying Environments](https://eslint.org/docs/user-guide/configuring#specifying-environments)


ESLint basic 

`eslint filename.js`
`eslint --fix filename.js`

Setup VSCode 

Open Extension
`Shift+Command+X`

## Introduction 

Executing Javascript through NodeJS

config to create an alias
`git config --global alias.lg "log --oneline --all --graph --decorate"`


github collaboration exercise 
create new local repo
`git init`
`touch README.md`
add and commit
create repo in github 
sync local to remote

If error occured Github “fatal: remote origin already exists”
`git remote set-url origin git@github.com:ppreyer/first_app.git`

This can discard uncommitted changes 
`git checkout -- <filename>`

Auto create boiler plate
Typing `!` and hitting `<tab>`