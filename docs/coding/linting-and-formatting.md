---
description: >-
  Setting up linters and code formatters is really important to group projects.
  When people are doing things like using different kinds of quotes, or people
  are following different semicolon rules, code
---

# Linting and Formatting

## Linting and Formatting

### Setting Up ESLint And Prettier

![eslint and prettier](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmiro.medium.com%2Fmax%2F1328%2F1*fA65R1umkZBVJjyBTTy6Xw.png&f=1&nofb=1)

#### Objective

Setting up linters and code formatters is really important to group projects. When people are doing things like using different kinds of quotes, or people are following different semicolon rules, code can become a confusing mess real quick. Adding things like code formatters and linters can be really beneficial to building a uniform and readable code base. This guide aims to help you easily set these things up in your groups project.

**Technologies Discussed**

* ESLint
* Prettier

**References**

* [ESLint Docs](https://eslint.org/)
* [ESLint VS Code Extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* [Prettier Docs](https://prettier.io/)
* [Prettier VS Code Extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

#### Install ESLint and Prettier VS Code Extensions

Make sure every team member has [prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) and [eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) VS Code extension's installed.

By default, most Labs projects will have both already in the `DevDependancies`with a Labs config in place. In these cases you can simply run `npm run lint` to view any errors or warnings and `npm run lint:fix` will attempt to fix them

{% hint style="info" %}
It's recommended to turn "Format On Save" on. Click on prettier link above and search for "Format On Save" for instructions on setting that up in vs code. Also, check out section "Linter Integration". 🔥
{% endhint %}

#### Configure ESLint and Prettier

Now we need to add dependencies to our project with some rc files! Woo hoo! 👏

In the root of your project's directory run:

`npm i eslint prettier eslint-config-prettier eslint-plugin-prettier`

{% hint style="info" %}
For react apps, add `eslint-plugin-react` to dependencies as well! Then we can add a file named `.eslintrc.js` with the following content for a react app.
{% endhint %}

**Example React Config**

```javascript
module.exports = {
  env: {
    commonjs: true,
    browser: true,
    es6: true,
    node: true,
  },
  extends: [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:prettier/recommended",
  ],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: "module",
  },
  plugins: ["react", "prettier"],
  rules: {},
  overrides: [
    {
      files: ["**/*.test.js"],
      env: {
        jest: true,
      },
    },
  ],
};
```

**Example Node Config**

```javascript
module.exports = {
  env: {
    node: true,
    commonjs: true,
    es6: true,
  },
  extends: ["eslint:recommended", "plugin:prettier/recommended"],
  parserOptions: {
    ecmaFeatures: {
    ecmaVersion: 2018,
    sourceType: "module",
  },
  plugins: ["prettier"],
  rules: {},
  overrides: [
    {
      files: ["**/*.test.js"],
      env: {
        jest: true,
      },
    },
  ],
};
```

By adding `.prettierrc.js` to our root with the following content for both React and Node projects, then the whole team will have shared formatter rules.

```javascript
module.exports = {
  trailingComma: "es5",
  tabWidth: 2,
  semi: true,
  singleQuote: true,
};
```

Then we can add some scripts to our `package.json`.

```javascript
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint --fix .",
    "format": "prettier --write \"**/*.+(js|jsx|json|yml|yaml|css|md)\""
  }
}
```

#### Conclusion

Setting up ESLint and Prettier in your projects can go a long way in helping you write better, more readable code. Even more so when you're working in a team environment.

You may have noticed that the "rules" key's where empty in the .eslintrc examples. ESLint does a lot by default but if you want more in-depth, fine grain control over the coding style for your project visit their [docs on rules here!](https://eslint.org/docs/rules/)

