.eslintrc
================

This dotfile is used for enforcing code style on our Javascript apps, the goal of using this is to maintain consistency between different repositories

ESLint?
-------

ESLint stands for EcmaScript Lint and is one of the three popular choices for linting Javascript code (JSLint, JSHint).

Why not the other options?
--------------------------

**JsHint:** JsHint is currently the most popular option, the reason of why we are not using JsHint is because it does not enforce much code style but rather avoids common errors. Simply put it allows style inconsistency

**JsLint:** Created by Douglas Crockford, it is a much more style-involved tool, though current implementations are not configurable enough, leaving space to error reporting in places where there's nothing to do about it.