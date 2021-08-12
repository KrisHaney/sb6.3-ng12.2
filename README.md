# Minimal reproduction repo

Shows global styles not working in Storybook 6.3 with Angular 12.2

When working (in ng 12.1), buttons in the button story are rotated by 180deg and uppercased

## Steps to reproduce

### Initialize the project

`npx sb@next repro`

(from [here](https://storybook.js.org/docs/angular/contribute/how-to-reproduce))

### Upgrade angular from 11 to 12

`ng update @angular/core@12 @angular/cli@12`

(from [here](https://update.angular.io/?v=11.0-12.0))

### Install webpack 5 and middleware

`yarn add webpack@5 --dev`

`yarn add @storybook/builder-webpack5@next @storybook/manager-webpack5@next --dev`

Add to .storybook/main.js
```js
module.exports = {
  core: {
    builder: 'webpack5',
  }
};
```

(from [here](https://github.com/storybookjs/storybook/blob/next/MIGRATION.md#angular-12-upgrade))

### Add global styles

Create `.storybook/global-styles.scss` and add some test styles

Add `import './global-styles.scss';` to `.storybook/preview.js`

