Finciero Javascript Style Guide
===============================

We based our style guide on the [Airbnb Javascript Style Guide](https://github.com/airbnb/javascript). In this document we only specify rules in which we disagree.

## Rules

- Avoid using trailing commma. eslint: [`comma-dangle`](http://eslint.org/docs/rules/comma-dangle.html).

```javascript
// bad
const hero = {
  firstName: 'Dana',
  lastName: 'Scully',
};

const heroes = [
  'Batman',
  'Superman',
];

// good
const hero = {
  firstName: 'Dana',
  lastName: 'Scully'
};

const heroes = [
  'Batman',
  'Superman'
];

```

- Avoid declaring function that receive more than 3 arguments. If you need to pass more arguments, pass them as an object.

```javascript
// bad
function foo(var1, var2, var3, var4) {
// ...
}

// good
function foo(args) {
// ..
}
```

- When an Arrow Function receive only one paramters should not be surrounded with parenthesis.

```javascript
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// better
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});

// good
[1, 2, 3].map(x => {
  const y = x + 1;
  return x * y;
});
```

- We use special rules for using the `let` variable declaration. All variables declared with `let` must be declared at the beginning of the scope.

```javascript

// bad
function foo() {
  let bar = 1;

  // code ...

  if (/* some condition */) {
    baz = functionCall();
    for (; baz < 100;) {
     baz = baz + functionCall();
    }
    bar += baz;
  }

  return bar;
}

// good
function foo() {
  let bar;

  bar = 1;

  // code ...

  if (/* some condition */) {
    let baz = functionCall();
    for (; baz < 100;) {
     baz = baz + functionCall();
    }
    bar += baz;
  }

  return bar;
}
```

- No blank lines inside array and objects.

```javascript
// bad
const obj = {
  foo() {
  },

  bar() {
  },
};

// good
const obj = {
  foo() {
  },
  bar() {
  },
};

// bad
const arr = [
  function foo() {
  },

  function bar() {
  },
];

// good
const arr = [
  function foo() {
  },
  function bar() {
  },
];
```
- Also remember not to **fight!**

Also you need to install the following packages to use our `.eslintrc`.

    npm install --save-dev eslint-config-airbnb eslint-plugin-react eslint

.eslintrc
=========

This dotfile is used for enforcing code style on our Javascript apps, the goal of using this is to maintain consistency between different repositories

ESLint?
-------

ESLint stands for EcmaScript Lint and is one of the three popular choices for linting Javascript code (JSLint, JSHint).

Why not the other options?
--------------------------

**JsHint:** JsHint is currently the most popular option, the reason of why we are not using JsHint is because it does not enforce much code style but rather avoids common errors. Simply put it allows style inconsistency

**JsLint:** Created by Douglas Crockford, it is a much more style-involved tool, though current implementations are not configurable enough, leaving space to error reporting in places where there's nothing to do about it.
