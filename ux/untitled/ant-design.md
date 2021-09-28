# Ant Design



## Ant Design of React

Following the Ant Design specification, we developed a React UI library `antd` that contains a set of high quality components and demos for building rich, interactive user interfaces.![](https://gw.alipayobjects.com/zos/rmsportal/KDpgvguMpGfqaHPjicRK.svg)+![](https://gw.alipayobjects.com/zos/antfincdn/aPkFc8Sj7n/method-draw-image.svg)

* [✨ Features](https://ant.design/docs/react/introduce#%E2%9C%A8-Features)
* [Environment Support](https://ant.design/docs/react/introduce#Environment-Support)
* [Version](https://ant.design/docs/react/introduce#Version)
* [Installation](https://ant.design/docs/react/introduce#Installation)
* [Usage](https://ant.design/docs/react/introduce#Usage)
* [Links](https://ant.design/docs/react/introduce#Links)
* [Companies using antd](https://ant.design/docs/react/introduce#Companies-using-antd)
* [Contributing](https://ant.design/docs/react/introduce#Contributing)
* [Need Help?](https://ant.design/docs/react/introduce#Need-Help?)

### ✨ Features[\#](https://ant.design/docs/react/introduce#%E2%9C%A8-Features) <a id="&#x2728;-Features"></a>

* 🌈 Enterprise-class UI designed for web applications.
* 📦 A set of high-quality React components out of the box.
* 🛡 Written in TypeScript with predictable static types.
* ⚙️ Whole package of design resources and development tools.
* 🌍 Internationalization support for dozens of languages.
* 🎨 Powerful theme customization in every detail.

### Environment Support[\#](https://ant.design/docs/react/introduce#Environment-Support) <a id="Environment-Support"></a>

* Modern browsers and Internet Explorer 11 \(with [polyfills](https://ant.design/docs/react/getting-started#Compatibility)\)
* Server-side Rendering
* [Electron](https://www.electronjs.org/)

| [![IE / Edge](https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png)](http://godban.github.io/browsers-support-badges/) IE / Edge | [![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png)](http://godban.github.io/browsers-support-badges/) Firefox | [![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png)](http://godban.github.io/browsers-support-badges/) Chrome | [![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png)](http://godban.github.io/browsers-support-badges/) Safari | [![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png)](http://godban.github.io/browsers-support-badges/) Opera | [![Electron](https://raw.githubusercontent.com/alrra/browser-logos/master/src/electron/electron_48x48.png)](http://godban.github.io/browsers-support-badges/) Electron |
| :--- | :--- | :--- | :--- | :--- | :--- |
| IE11, Edge | last 2 versions | last 2 versions | last 2 versions | last 2 versions | last 2 versions |

Polyfills are needed for IE browsers. We recommend [@babel/preset-env](https://babeljs.io/docs/en/babel-preset-env) for it. You can set `targets` config if you are using [umi](http://umijs.org/).

> We drop support of IE8 after `antd@2.0`, We drop support of React 15 and IE9/10 after `antd@4.0`,

### Version[\#](https://ant.design/docs/react/introduce#Version) <a id="Version"></a>

* Stable: [![npm package](https://img.shields.io/npm/v/antd.svg?style=flat-square)](https://www.npmjs.org/package/antd)

You can subscribe to this feed for new version notifications: [https://github.com/ant-design/ant-design/releases.atom](https://github.com/ant-design/ant-design/releases.atom)

### Installation[\#](https://ant.design/docs/react/introduce#Installation) <a id="Installation"></a>

#### Using npm or yarn[\#](https://ant.design/docs/react/introduce#Using-npm-or-yarn) <a id="Using-npm-or-yarn"></a>

**We recommend using npm or yarn to install**, it not only makes development easier, but also allow you to take advantage of the rich ecosystem of Javascript packages and tooling.

```text
$ npm install antd
```

```text
$ yarn add antd
```

If you are in a bad network environment, you can try other registries and tools like [cnpm](https://github.com/cnpm/cnpm).

#### Import in Browser[\#](https://ant.design/docs/react/introduce#Import-in-Browser) <a id="Import-in-Browser"></a>

Add `script` and `link` tags in your browser and use the global variable `antd`.

We provide `antd.js` `antd.css` and `antd.min.js` `antd.min.css` under `antd/dist` in antd's npm package. You can also download these files directly from [![CDNJS](https://img.shields.io/cdnjs/v/antd.svg?style=flat-square)](https://cdnjs.com/libraries/antd), [![](https://data.jsdelivr.com/v1/package/npm/antd/badge)](https://www.jsdelivr.com/package/npm/antd) or [unpkg](https://unpkg.com/antd/dist).

> **We strongly discourage loading the entire files** this will add bloat to your application and make it more difficult to receive bugfixes and updates. Antd is intended to be used in conjunction with a build tool, such as [webpack](https://webpack.github.io/), which will make it easy to import only the parts of antd that you are using.
>
> Note: you should import react/react-dom/moment before using antd.js.

### Usage[\#](https://ant.design/docs/react/introduce#Usage) <a id="Usage"></a>

```text
import { DatePicker } from 'antd';

ReactDOM.render(<DatePicker />, mountNode);
```

And import stylesheets manually:

```text
import 'antd/dist/antd.css'; // or 'antd/dist/antd.less'
```

#### Use modularized antd[\#](https://ant.design/docs/react/introduce#Use-modularized-antd) <a id="Use-modularized-antd"></a>

`antd` supports ES modules tree shaking by default for JS part.

#### TypeScript[\#](https://ant.design/docs/react/introduce#TypeScript) <a id="TypeScript"></a>

`antd` provides a built-in ts definition, don't install `@types/antd`.

### Links[\#](https://ant.design/docs/react/introduce#Links) <a id="Links"></a>

* [Home page](https://ant.design/)
* [Components](https://ant.design/components/overview/)
* [Ant Design Pro](https://pro.ant.design/)
* [Ant Design Charts](https://charts.ant.design/)
* [Change Log](https://ant.design/changelog)
* [rc-components](http://react-component.github.io/)
* [Mobile UI](http://mobile.ant.design/)
* [Ant Design Icons](https://github.com/ant-design/ant-design-icons)
* [Ant Design Colors](https://github.com/ant-design/ant-design-colors)
* [Ant Design Pro Layout](https://github.com/ant-design/ant-design-pro-layout)
* [Ant Design Pro Blocks](https://github.com/ant-design/pro-blocks)
* [Dark Theme](https://github.com/ant-design/ant-design-dark-theme)
* [Landing Pages](https://landing.ant.design/)
* [Motion](https://motion.ant.design/)
* [Scaffold Market](http://scaffold.ant.design/)
* [Developer Instruction](https://github.com/ant-design/ant-design/wiki/Development)
* [Versioning Release Note](https://github.com/ant-design/ant-design/wiki/%E8%BD%AE%E5%80%BC%E8%A7%84%E5%88%99%E5%92%8C%E7%89%88%E6%9C%AC%E5%8F%91%E5%B8%83%E6%B5%81%E7%A8%8B)
* [FAQ](https://ant.design/docs/react/faq)
* [CodeSandbox Template](https://u.ant.design/codesandbox-repro) for bug reports
* [Awesome Ant Design](https://github.com/websemantics/awesome-ant-design)
* [Customize Theme](https://ant.design/docs/react/customize-theme)
* [How to Apply for Being A Collaborator](https://github.com/ant-design/ant-design/wiki/Collaborators#how-to-apply-for-being-a-collaborator)





## Getting Started

Ant Design React is dedicated to providing a **good development experience** for programmers. Before starting, it is recommended to learn [React](https://reactjs.org/) and [ES2015](http://babeljs.io/docs/learn-es2015/) first, and correctly install and configure [Node.js](https://nodejs.org/) v8 or above.

The official guide also assumes that you have intermediate knowledge about HTML, CSS, and JavaScript, and React. If you are just starting to learn front-end or React, it may not be the best idea to use the UI framework as your first step.

Finally, if you are working in a local development environment, please refer to [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) section of "Use in create-react-app".

* [Your First Example](https://ant.design/docs/react/getting-started#Your-First-Example)
* [Test with Jest](https://ant.design/docs/react/getting-started#Test-with-Jest)
* [Import on Demand](https://ant.design/docs/react/getting-started#Import-on-Demand)
* [Customize your Workflow](https://ant.design/docs/react/getting-started#Customize-your-Workflow)

### Your First Example[\#](https://ant.design/docs/react/getting-started#Your-First-Example) <a id="Your-First-Example"></a>

Here is a simple online codesandbox demo of an Ant Design component to show the usage of Ant Design React.

Follow the steps below to play around with Ant Design yourself:

#### 1. Create a codesandbox[\#](https://ant.design/docs/react/getting-started#1.-Create-a-codesandbox) <a id="1.-Create-a-codesandbox"></a>

Visit [http://u.ant.design/codesandbox-repro](http://u.ant.design/codesandbox-repro) to create a codesandbox -- don't forget to press the save button as well to create a new instance.

#### 2. Use and modify an antd component[\#](https://ant.design/docs/react/getting-started#2.-Use-and-modify-an-antd-component) <a id="2.-Use-and-modify-an-antd-component"></a>

Replace the contents of `index.js` with the following code. As you can see, there is no difference between antd's components and typical React components.

If you have already set things up by following the [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) section of "Use in create-react-app", replace the content of `/src/index.js` as follows:

```text
import React, { useState } from 'react';
import { render } from 'react-dom';
import { DatePicker, message } from 'antd';
import 'antd/dist/antd.css';
import './index.css';

const App = () => {
  const [date, setDate] = useState(null);
  const handleChange = value => {
    message.info(`Selected Date: ${value ? value.format('YYYY-MM-DD') : 'None'}`);
    setDate(value);
  };
  return (
    <div style={{ width: 400, margin: '100px auto' }}>
      <DatePicker onChange={handleChange} />
      <div style={{ marginTop: 16 }}>
        Selected Date: {date ? date.format('YYYY-MM-DD') : 'None'}
      </div>
    </div>
  );
};

render(<App />, document.getElementById('root'));
```

#### 3. Explore more components[\#](https://ant.design/docs/react/getting-started#3.-Explore-more-components) <a id="3.-Explore-more-components"></a>

You can view the list of components in the side menu of the Components page, such as the [Alert](https://ant.design/components/alert/) component. Plenty of examples are also provided in the component pages and API documentation as well.

Click the "Open in Editor" icon in the first example to open an editor with source code to use out-of-the-box. Now you can import the `Alert` component into the codesandbox:

```text
- import { DatePicker, message } from 'antd';
+ import { DatePicker, message, Alert } from 'antd';
```

Now add the following jsx inside the `render` function.

```text
  <DatePicker onChange={value => this.handleChange(value)} />
  <div style={{ marginTop: 20 }}>
-   Selected Date: {date ? date.format('YYYY-MM-DD') : 'None'}
+   <Alert message="Selected Date" description={date ? date.format('YYYY-MM-DD') : 'None'} />
  </div>
```

Select a date, and you can see the effect in the preview area on the right:

![codesandbox screenshot](https://gw.alipayobjects.com/zos/antfincdn/JrXptUm1Nz/6b50edc4-3a3c-4b2a-843e-f9f0af2c4667.png)

OK! Now that you know the basics of using antd components, you are welcome to explore more components in the codesandbox. When reporting a bug with ant design, we also strongly recommend using codesandbox to provide a reproducible demo as well.

#### 4. Next Steps[\#](https://ant.design/docs/react/getting-started#4.-Next-Steps) <a id="4.-Next-Steps"></a>

During actual real-world project development, you will most likely need a development workflow consisting of `compile/build/deploy/lint/debug/` deployment. You can read the following documents on the subject or use the following scaffolds and examples provided below:

* [Ant Design Pro](http://pro.ant.design/)
* [antd-admin](https://github.com/zuiidea/antd-admin)
* [d2-admin](https://github.com/d2-projects/d2-admin)
* More scaffolds at [Scaffold Market](http://scaffold.ant.design/)

### Test with Jest[\#](https://ant.design/docs/react/getting-started#Test-with-Jest) <a id="Test-with-Jest"></a>

If you use `create-react-app` follow the instructions [here](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest) instead.

Jest does not support `esm` modules, and Ant Design uses them. In order to test your Ant Design application with Jest you have to add the following to your Jest config :

```text
"transform": { "^.+\\.(ts|tsx|js|jsx)?$": "ts-jest" }
```

### Import on Demand[\#](https://ant.design/docs/react/getting-started#Import-on-Demand) <a id="Import-on-Demand"></a>

`antd` supports tree shaking of ES modules, so using `import { Button } from 'antd';` would drop js code you didn't use.

If you see logs like in the screenshot below, you might still be using `webpack@1.x` or have a wrong webpack config which can't support tree shaking.

```text
You are using a whole package of antd, please use https://www.npmjs.com/package/babel-plugin-import to reduce app bundle size. Please upgrade webpack or check the config.
```

> ![console warning](https://zos.alipayobjects.com/rmsportal/GHIRszVcmjccgZRakJDQ.png)

### Customize your Workflow[\#](https://ant.design/docs/react/getting-started#Customize-your-Workflow) <a id="Customize-your-Workflow"></a>

If you want to customize your workflow, we recommend using [webpack](http://webpack.github.io/) to build and debug code. You can try out plenty of [boilerplates](https://github.com/enaqx/awesome-react#react-tools) available in the React ecosystem.

There are also some [scaffolds](http://scaffold.ant.design/) which have already been integrated into antd, so you can try and start with one of these and even contribute.



## Real project with umi

* [Install Umi](https://ant.design/docs/react/practical-projects#Install-Umi)
* [Create Routes](https://ant.design/docs/react/practical-projects#Create-Routes)
* [Write UI Components](https://ant.design/docs/react/practical-projects#Write-UI-Components)
* [Simple data management solution](https://ant.design/docs/react/practical-projects#Simple-data-management-solution)
* [ProLayout](https://ant.design/docs/react/practical-projects#ProLayout)
* [ProTable](https://ant.design/docs/react/practical-projects#ProTable)
* [Build](https://ant.design/docs/react/practical-projects#Build)
* [What's Next](https://ant.design/docs/react/practical-projects#What's-Next)

In real project development, you may need data flow solutions such as Redux or MobX. Ant Design React is a UI library that can be used with data flow solutions and application frameworks in any React ecosystem. Based on the business scenario, we launched a pluggable enterprise-level application framework umi, which is recommended for use in the project.

And [umi](https://umijs.org/) is a routing-based framework that supports [next.js-like conventional routing](https://umijs.org/docs/convention-routing) and various advanced routing functions, such as [routing-level on-demand loading](https://umijs.org/config#dynamicimport). With a complete [plugin system](https://umijs.org/plugins/api) that covers every life cycle from source code to build product, umi is able to support various functional extensions and business needs; meanwhile [Umi UI](https://umijs.org/docs/use-umi-ui) is provided to enhance the development experience and development efficiency through Visual Aided Programming \(VAP\).

> You may also be interested in [Ant Design Pro](https://pro.ant.design/), an Out-of-box UI solution for enterprise applications based on umi, dva and ant design.

This article will guide you to create a simple application from zero using Umi, dva and antd.

### Install Umi[\#](https://ant.design/docs/react/practical-projects#Install-Umi) <a id="Install-Umi"></a>

It is recommended to use yarn to create an application and execute the following command.

```text
$ mkdir myapp && cd myapp
$ yarn create @umijs/umi-app
$ yarn
```

> If you use npm, you can execute `npx @umijs/create-umi-app` with the same effect.
>
> And if you want to use a fixed version of antd, you can install additional antd dependency in your project, and the antd dependencies declared in package.json will be used first.

### Create Routes[\#](https://ant.design/docs/react/practical-projects#Create-Routes) <a id="Create-Routes"></a>

We need to write an application displaying the list of products. The first step is to create a route.

If you don't have npx, you need to install it first to execute the commands under node\_modules.

```text
$ yarn global add npx
```

Then create a `/products` route,

```text
$ npx umi g page products --typescript

Write: src/pages/products.tsx
Write: src/pages/products.css
```

In `.umirc.ts` configured in routing, if there is need to internationalization, can configure `locale` enable antd internationalization:

```text
import { defineConfig } from 'umi';

export default defineConfig({
+ locale: { antd: true },
  routes: [
    { path: '/', component: '@/pages/index' },
+   { path: '/products', component: '@/pages/products' },
  ],
});
```

run `yarn start` then open [http://localhost:8000/products](http://localhost:8000/products) in your browser and you should see the corresponding page.

### Write UI Components[\#](https://ant.design/docs/react/practical-projects#Write-UI-Components) <a id="Write-UI-Components"></a>

As your application grows and you notice you are sharing UI elements between multiple pages \(or using them multiple times on the same page\), in umi it's called reusable components.

Let's create a `ProductList` component that we can use in multiple places to show a list of products.

Create `src/components/ProductList.tsx` by typing:

```text
import { Table, Popconfirm, Button } from 'antd';

const ProductList = ({ onDelete, products }) => {
  const columns = [
    {
      title: 'Name',
      dataIndex: 'name',
    },
    {
      title: 'Actions',
      render: (text, record) => {
        return (
          <Popconfirm title="Delete?" onConfirm={() => onDelete(record.id)}>
            <Button>Delete</Button>
          </Popconfirm>
        );
      },
    },
  ];
  return <Table dataSource={products} columns={columns} />;
};

export default ProductList;
```

### Simple data management solution[\#](https://ant.design/docs/react/practical-projects#Simple-data-management-solution) <a id="Simple-data-management-solution"></a>

`@umijs/plugin-model` is a simple data flow scheme based on the hooks paradigm, which can replace dva to perform global data flow in the middle stage under certain circumstances. We agree that the files in the `src/models` directory are the model files defined by the project. Each file needs to export a function by default, the function defines a hook, and files that do not meet the specifications will be filtered out.

The file name corresponds to the name of the final model, and you can consume the data in the model through the API provided by the plug-in.

Let's take a simple table as an example. First you need to create a new file `src/models/useProductList.ts`.

```text
import { useRequest } from 'umi';
import { queryProductList } from '@/services/product';

export default function useProductList(params: { pageSize: number; current: number }) {
  const msg = useRequest(() => queryUserList(params));

  const deleteProducts = async (id: string) => {
    try {
      await removeProducts(id);
      message.success('success');
      msg.run();
    } catch (error) {
      message.error('fail');
    }
  };

  return {
    dataSource: msg.data,
    reload: msg.run,
    loading: msg.loading,
    deleteProducts,
  };
}
```

Edit `src/pages/products.tsx` and replace with the following:

```text
import { useModel } from 'umi';
import ProductList from '@/components/ProductList';

const Products = () => {
  const { dataSource, reload, deleteProducts } = useModel('useProductList');
  return (
    <div>
      <a onClick={() => reload()}>reload</a>
      <ProductList onDelete={deleteProducts} products={dataSource} />
    </div>
  );
};

export default Products;
```

Refresh your browser, you should see the following result:

![](https://gw.alipayobjects.com/zos/antfincdn/dPsy4tFHN3/umi.gif)

### ProLayout[\#](https://ant.design/docs/react/practical-projects#ProLayout) <a id="ProLayout"></a>

A standard mid-to-back page generally requires a layout. This layout is often highly similar. ProLayout encapsulates commonly used menus, breadcrumbs, page headers and other functions, provides an independent framework and works out of the box Advanced layout components.

And supports three modes of `side`, `mix`, and `top`, and it also has built-in menu selection, the menu generates breadcrumbs, and automatically sets the logic of the page title. Can help you start a project quickly.

![site](https://gw.alipayobjects.com/zos/antfincdn/gXkuc%26RmT7/64038246-E2BF-4840-8898-5AF531897A44.png)

The method of use is also extremely simple, requiring only a few simple settings.

```text
import { Button } from 'antd';
import ProLayout, { PageContainer } from '@ant-design/pro-layout';

export default (
  <ProLayout>
    <PageContainer
      extra={[
        <Button key="3">Operating</Button>,
        <Button key="2">Operating</Button>,
        <Button key="1" type="primary">
          Main Operating
        </Button>,
      ]}
      footer={[<Button>reset</Button>, <Button type="primary">submit</Button>]}
    >
      {children}
    </PageContainer>
  </ProLayout>
);
```

Click here [Quick Start](https://prolayout.ant.design/getting-started).

### ProTable[\#](https://ant.design/docs/react/practical-projects#ProTable) <a id="ProTable"></a>

Many data in an admin page does not need to be shared across pages, and models are sometimes not needed.

```text
import ProTable from '@ant-design/pro-table';
import { Popconfirm, Button } from 'antd';
import { queryProductList } from '@/services/product';

const Products = () => {
  const actionRef = useRef<ActionType>();

  const deleteProducts = async (id: string) => {
    try {
      await removeProducts(id);
      message.success('success');
      actionRef.current?.reload();
    } catch (error) {
      message.error('fail');
    }
  };

  const columns = [
    {
      title: 'Name',
      dataIndex: 'name',
    },
    {
      title: 'Actions',
      render: (text, record) => {
        return (
          <Popconfirm title="Delete?" onConfirm={() => onDelete(record.id)}>
            <Button>Delete</Button>
          </Popconfirm>
        );
      },
    },
  ];

  return (
    <ProTable<{ name: string }>
      headerTitle="Query Table"
      actionRef={actionRef}
      rowKey="name"
      request={(params, sorter, filter) => queryProductList({ ...params, sorter, filter })}
      columns={columns}
    />
  );
};
```

ProTable provides preset logic to handle loading, pagination and search forms, which can greatly reduce the amount of code, click here [Quick Start](https://protable.ant.design/getting-started).

### Build[\#](https://ant.design/docs/react/practical-projects#Build) <a id="Build"></a>

Now that we've written our application and verified that it works in development, it's time to get it ready for deployment to our users. To do so, execute the following command:

```text
$ yarn build
```

![](https://gw.alipayobjects.com/zos/antfincdn/Zd3f%242NdOK/b911d244-f1a5-4d61-adc5-3710cd86cd1b.png)

The `build` command packages up all of the assets that make up your application —— JavaScript, templates, CSS, web fonts, images, and more. Then you can find these files in the `dist/` directory.

### What's Next[\#](https://ant.design/docs/react/practical-projects#What's-Next) <a id="What&apos;s-Next"></a>

We have completed a simple application, but you may still have lots of questions, such as:

* How to handle onError globally and locally?
* How to handle routes?
* How to mock data?
* How to deploy?
* ant so on...

You can:

* Visit [umi official website](https://umijs.org/) and [dva official website](https://dvajs.com/)
* Know [the umi routes](https://umijs.org/zh/guide/router.html)
* Know [how to deploy umi application](https://umijs.org/zh/guide/deploy.html)
* Scaffolding out of the box [Ant Design Pro](https://pro.ant.design/)
* Advanced Layout [ProLayout](https://prolayout.ant.design/)
* Advanced Table [ProTable](https://protable.ant.design/)





## Use in create-react-app

[create-react-app](https://github.com/facebookincubator/create-react-app) is one of the best React application development tools. We are going to use `antd` within it and modify the webpack config for some customized needs.

* [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization)
* [Import antd](https://ant.design/docs/react/use-with-create-react-app#Import-antd)
* [Test with Jest](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest)
* [Advanced Guides](https://ant.design/docs/react/use-with-create-react-app#Advanced-Guides)
* [eject](https://ant.design/docs/react/use-with-create-react-app#eject)
* [Summary](https://ant.design/docs/react/use-with-create-react-app#Summary)

### Install and Initialization[\#](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) <a id="Install-and-Initialization"></a>

Before all start, you may need install [yarn](https://github.com/yarnpkg/yarn/).

```text
$ yarn create react-app antd-demo

# or

$ npx create-react-app antd-demo
```

The tool will create and initialize environment and dependencies automatically, please try config your proxy setting or use another npm registry if any network errors happen during it.

Then we go inside `antd-demo` and start it.

```text
$ cd antd-demo
$ yarn start
```

Open the browser at [http://localhost:3000/](http://localhost:3000/). It renders a header saying "Welcome to React" on the page.

### Import antd[\#](https://ant.design/docs/react/use-with-create-react-app#Import-antd) <a id="Import-antd"></a>

Below is the default directory structure.

```text
├── README.md
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
├── src
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   └── logo.svg
└── yarn.lock
```

Now we install `antd` from yarn or npm.

```text
$ yarn add antd
```

Modify `src/App.js`, import Button component from `antd`.

```text
import React from 'react';
import { Button } from 'antd';
import './App.css';

const App = () => (
  <div className="App">
    <Button type="primary">Button</Button>
  </div>
);

export default App;
```

Add `antd/dist/antd.css` at the top of `src/App.css`.

```text
@import '~antd/dist/antd.css';
```

Ok, you should now see a blue primary button displayed on the page. Next you can choose any components of `antd` to develop your application. Visit other workflows of `create-react-app` at its [User Guide](https://create-react-app.dev/docs/getting-started).

We are successfully running antd components now, go build your own application!

### Test with Jest[\#](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest) <a id="Test-with-Jest"></a>

`create-react-app` comes with `jest` built in. Jest does not support `esm` modules, and Ant Design uses them. In order to test your Ant Design application with Jest you have to add the following to your `package.json` :

```text
"jest": {
  "transformIgnorePatterns": [
    "/node_modules/(?!antd|@ant-design|rc-.+?|@babel/runtime).+(js|jsx)$"
  ]
}
```

### Advanced Guides[\#](https://ant.design/docs/react/use-with-create-react-app#Advanced-Guides) <a id="Advanced-Guides"></a>

In the real world, we usually have to modify default webpack config for custom needs such as themes. We can achieve that by using [craco](https://github.com/gsoft-inc/craco) which is one of create-react-app's custom config solutions.

Install craco and modify the `scripts` field in `package.json`.

```text
$ yarn add @craco/craco
```

```text
/* package.json */
"scripts": {
-   "start": "react-scripts start",
-   "build": "react-scripts build",
-   "test": "react-scripts test",
+   "start": "craco start",
+   "build": "craco build",
+   "test": "craco test",
}
```

Then create a `craco.config.js` at root directory of your project for further overriding.

```text
/* craco.config.js */
module.exports = {
  // ...
};
```

#### Customize Theme[\#](https://ant.design/docs/react/use-with-create-react-app#Customize-Theme) <a id="Customize-Theme"></a>

According to the [Customize Theme documentation](https://ant.design/docs/react/customize-theme), we need to modify less variables via loader like [less-loader](https://github.com/webpack/less-loader). We can use [craco-less](https://github.com/DocSpring/craco-less) to achieve that,

First we should modify `src/App.css` to `src/App.less`, then import less file instead.

```text
/* src/App.js */
- import './App.css';
+ import './App.less';
```

```text
/* src/App.less */
- @import '~antd/dist/antd.css';
+ @import '~antd/dist/antd.less';
```

Then install `craco-less` and modify `craco.config.js` like below.

```text
$ yarn add craco-less
```

```text
const CracoLessPlugin = require('craco-less');

module.exports = {
  plugins: [
    {
      plugin: CracoLessPlugin,
      options: {
        lessLoaderOptions: {
          lessOptions: {
            modifyVars: { '@primary-color': '#1DA57A' },
            javascriptEnabled: true,
          },
        },
      },
    },
  ],
};
```

By adding `modifyVars` option of [less-loader](https://github.com/webpack/less-loader#less-options) here, we should see a green button rendered on the page after rebooting the server now.

We provide built-in dark theme and compact theme in antd, you can reference to [Use dark or compact theme](https://ant.design/docs/react/customize-theme#Use-dark-or-compact-theme).

> You could also try [react-app-rewired](https://github.com/timarney/react-app-rewired) and [customize-cra](https://github.com/arackaf/customize-cra) to customize create-react-app webpack config like craco did.

### eject[\#](https://ant.design/docs/react/use-with-create-react-app#eject) <a id="eject"></a>

You can also eject your application using [yarn run eject](https://facebook.github.io/create-react-app/docs/available-scripts#npm-run-eject) for a custom setup of create-react-app, although you should dig into it by yourself.

### Summary[\#](https://ant.design/docs/react/use-with-create-react-app#Summary) <a id="Summary"></a>

Finally, we used antd with create-react-app successfully, the source code of this guide was pushed to [create-react-app-antd](https://github.com/ant-design/create-react-app-antd) which you could clone and use it directly.

Next part, We will introduce how to use antd in [TypeScript](https://ant.design/docs/react/use-in-typescript) and [Umi](https://ant.design/docs/react/practical-projects), let's keep moving!

* [ ](https://github.com/afc163)





## Customize Theme

* [Ant Design Less variables](https://ant.design/docs/react/customize-theme#Ant-Design-Less-variables)
* [How to do it](https://ant.design/docs/react/customize-theme#How-to-do-it)
* [How to avoid modifying global styles?](https://ant.design/docs/react/customize-theme#How-to-avoid-modifying-global-styles?)
* [Not working?](https://ant.design/docs/react/customize-theme#Not-working?)
* [Official Themes 🌈](https://ant.design/docs/react/customize-theme#Official-Themes-%F0%9F%8C%88)
* [Related Articles](https://ant.design/docs/react/customize-theme#Related-Articles)

Ant Design allows you to customize our design tokens to satisfy UI diversity from business or brand requirements, including primary color, border radius, border color, etc.

![customized themes](https://zos.alipayobjects.com/rmsportal/zTFoszBtDODhXfLAazfSpYbSLSEeytoG.png)

### Ant Design Less variables[\#](https://ant.design/docs/react/customize-theme#Ant-Design-Less-variables) <a id="Ant-Design-Less-variables"></a>

We are using [Less](http://lesscss.org/) as the development language for styling. A set of less variables are defined for each design aspect that can be customized to your needs.

There are some major variables below, all less variables could be found in [Default Variables](https://github.com/ant-design/ant-design/blob/master/components/style/themes/default.less).

```text
@primary-color: #1890ff; // primary color for all components
@link-color: #1890ff; // link color
@success-color: #52c41a; // success state color
@warning-color: #faad14; // warning state color
@error-color: #f5222d; // error state color
@font-size-base: 14px; // major text font size
@heading-color: rgba(0, 0, 0, 0.85); // heading text color
@text-color: rgba(0, 0, 0, 0.65); // major text color
@text-color-secondary: rgba(0, 0, 0, 0.45); // secondary text color
@disabled-color: rgba(0, 0, 0, 0.25); // disable state color
@border-radius-base: 2px; // major border radius
@border-color-base: #d9d9d9; // major border color
@box-shadow-base: 0 3px 6px -4px rgba(0, 0, 0, 0.12), 0 6px 16px 0 rgba(0, 0, 0, 0.08),
  0 9px 28px 8px rgba(0, 0, 0, 0.05); // major shadow for layers
```

Please report an issue if the existing list of variables is not enough for you.

### How to do it[\#](https://ant.design/docs/react/customize-theme#How-to-do-it) <a id="How-to-do-it"></a>

We will use [modifyVars](http://lesscss.org/usage/#using-less-in-the-browser-modify-variables) provided by less.js to override the default values of the variables, You can use this [example](https://github.com/ant-design/create-react-app-antd) as a live playground. We now introduce some popular way to do it depends on different workflow.

#### Customize in webpack[\#](https://ant.design/docs/react/customize-theme#Customize-in-webpack) <a id="Customize-in-webpack"></a>

We take a typical `webpack.config.js` file as example to customize its [less-loader](https://github.com/webpack-contrib/less-loader) options.

```text
// webpack.config.js
module.exports = {
  rules: [{
    test: /\.less$/,
    use: [{
      loader: 'style-loader',
    }, {
      loader: 'css-loader', // translates CSS into CommonJS
    }, {
      loader: 'less-loader', // compiles Less to CSS
+     options: {
+       lessOptions: { // If you are using less-loader@5 please spread the lessOptions to options directly
+         modifyVars: {
+           'primary-color': '#1DA57A',
+           'link-color': '#1DA57A',
+           'border-radius-base': '2px',
+         },
+         javascriptEnabled: true,
+       },
+     },
    }],
    // ...other rules
  }],
  // ...other config
}
```

Note:

1. Don't exclude `node_modules/antd` when using less-loader.
2. `lessOptions` usage is supported at [less-loader@6.0.0](https://github.com/webpack-contrib/less-loader/releases/tag/v6.0.0).

#### Customize in Umi[\#](https://ant.design/docs/react/customize-theme#Customize-in-Umi) <a id="Customize-in-Umi"></a>

You can easily use [theme](https://umijs.org/config/#theme) field in `.umirc.ts` or [config/config.ts](https://github.com/ant-design/ant-design-pro/blob/v5/config/config.ts) file of your project root directory if you are using [Umi](http://umijs.org/), which could be an object or a javascript file path.

```text
"theme": {
  "primary-color": "#1DA57A",
},
```

Or just [a javascript file path](https://github.com/ant-design/ant-design-pro/blob/b7e7983661eb5e53dc807452e9653e93e74276d4/.webpackrc.js#L18):

```text
"theme": "./theme.js",
```

#### Customize in create-react-app[\#](https://ant.design/docs/react/customize-theme#Customize-in-create-react-app) <a id="Customize-in-create-react-app"></a>

Follow [Use in create-react-app](https://ant.design/docs/react/use-with-create-react-app).

#### Customize in less file[\#](https://ant.design/docs/react/customize-theme#Customize-in-less-file) <a id="Customize-in-less-file"></a>

Another approach to customize theme is creating a `less` file within variables to override `antd.less`.

```text
@import '~antd/lib/style/themes/default.less';
@import '~antd/dist/antd.less'; // Import Ant Design styles by less entry
@import 'your-theme-file.less'; // variables to override above
```

Note: This way will load the styles of all components, regardless of your demand, which cause `style` option of `babel-plugin-import` not working.

#### Dynamic theme[\#](https://ant.design/docs/react/customize-theme#Dynamic-theme) <a id="Dynamic-theme"></a>

Runtime update theme color please [ref this doc](https://ant.design/docs/react/customize-theme-variable).

### How to avoid modifying global styles?[\#](https://ant.design/docs/react/customize-theme#How-to-avoid-modifying-global-styles) <a id="How-to-avoid-modifying-global-styles?"></a>

Currently ant-design is designed as a whole experience and modify global styles \(eg `body` etc\). If you need to integrate ant-design as a part of an existing website, it's likely you want to prevent ant-design to override global styles.

While there's no canonical way to do it, you can take one of the following paths :

#### Configure webpack to load an alternate less file and scope global styles[\#](https://ant.design/docs/react/customize-theme#Configure-webpack-to-load-an-alternate-less-file-and-scope-global-styles) <a id="Configure-webpack-to-load-an-alternate-less-file-and-scope-global-styles"></a>

It's possible to configure webpack to load an alternate less file:

```text
new webpack.NormalModuleReplacementPlugin( /node_modules\/antd\/lib\/style\/index\.less/, path.resolve(rootDir, 'src/myStylesReplacement.less') )

#antd { @import '~antd/lib/style/core/index.less'; @import '~antd/lib/style/themes/default.less'; }
```

Where the src/myStylesReplacement.less file loads the same files as the index.less file, but loads them within the scope of a top-level selector : the result is that all of the "global" styles are being applied with the \#antd scope.

#### Use a postcss processor to scope all styles[\#](https://ant.design/docs/react/customize-theme#Use-a-postcss-processor-to-scope-all-styles) <a id="Use-a-postcss-processor-to-scope-all-styles"></a>

See an example of usage with [gulp and postcss-prefixwrap](https://gist.github.com/sbusch/a90eafaf5a5b61c6d6172da6ff76ddaa).

### Not working?[\#](https://ant.design/docs/react/customize-theme#Not-working) <a id="Not-working?"></a>

You must import styles as less format. A common mistake would be importing multiple copied of styles that some of them are css format to override the less styles.

* If you import styles by specifying the `style` option of [babel-plugin-import](https://github.com/ant-design/babel-plugin-import), change it from `'css'` to `true`, which will import the `less` version of antd.
* If you import styles from `'antd/dist/antd.css'`, change it to `antd/dist/antd.less`.

### Official Themes 🌈[\#](https://ant.design/docs/react/customize-theme#Official-Themes-%F0%9F%8C%88) <a id="Official-Themes-&#x1F308;"></a>

We have some official themes, try them out and give us some feedback!

* 🌑 Dark Theme \(supported in 4.0.0+\)
* 📦 Compact Theme \(supported in 4.1.0+\)
* ☁️ [Aliyun Console Theme \(Beta\)](https://github.com/ant-design/ant-design-aliyun-theme)

#### Use dark or compact theme[\#](https://ant.design/docs/react/customize-theme#Use-dark-or-compact-theme) <a id="Use-dark-or-compact-theme"></a>

![](https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*mYU9R4YFxscAAAAAAAAAAABkARQnAQ)

Method 1: using Umi 3

If you're using [Umi 3](http://umijs.org/):

```text
// .umirc.ts or config/config.ts
export default {
  antd: {
    dark: true, // active dark theme
    compact: true, // active compact theme
  },
},
```

Method 2: Import [antd/dist/antd.dark.less](https://unpkg.com/browse/antd@4.x/dist/antd.dark.less) or [antd/dist/antd.compact.less](https://unpkg.com/browse/antd@4.x/dist/antd.compact.less) in the style file:

```text
@import '~antd/dist/antd.dark.less'; // Introduce the official dark less style entry file
@import '~antd/dist/antd.compact.less'; // Introduce the official compact less style entry file
```

If the project does not use Less, you can import [antd.dark.css](https://unpkg.com/browse/antd@4.x/dist/antd.dark.css) or [antd/dist/antd.compact.css](https://unpkg.com/browse/antd@4.x/dist/antd.compact.css) in the CSS file:

```text
@import '~antd/dist/antd.dark.css';
@import '~antd/dist/antd.compact.css';
```

> Note that you don't need to import `antd/dist/antd.less` or `antd/dist/antd.css` anymore, please remove it, and remove babel-plugin-import `style` config too. You can't enable two or more theme at the same time by this method.

Method 3: using [less-loader](https://github.com/webpack-contrib/less-loader) in `webpack.config.js` to introduce as needed:

```text
const { getThemeVariables } = require('antd/dist/theme');

// webpack.config.js
module.exports = {
  rules: [{
    test: /\.less$/,
    use: [{
      loader: 'style-loader',
    }, {
      loader: 'css-loader', // translates CSS into CommonJS
    }, {
      loader: 'less-loader', // compiles Less to CSS
+     options: {
+       lessOptions: { // If you are using less-loader@5 please spread the lessOptions to options directly
+         modifyVars: getThemeVariables({
+           dark: true, // Enable dark mode
+           compact: true, // Enable compact mode
+         }),
+         javascriptEnabled: true,
+       },
+     },
    }],
  }],
};
```

### Related Articles[\#](https://ant.design/docs/react/customize-theme#Related-Articles) <a id="Related-Articles"></a>

* [Using Ant Design in Sass-Styled Webpack Projects with `antd-scss-theme-plugin`](https://intoli.com/blog/antd-scss-theme-plugin/)
* [How to Customize Ant Design with React & Webpack… the Missing Guide](https://medium.com/@GeoffMiller/how-to-customize-ant-design-with-react-webpack-the-missing-guide-c6430f2db10f)
* [Theming Ant Design with Sass and Webpack](https://gist.github.com/Kruemelkatze/057f01b8e15216ae707dc7e6c9061ef7)
* [Using Sass/Scss with React App \(create-react-app\)](https://medium.com/@mzohaib.qc/using-sass-scss-with-react-app-create-react-app-d03072083ef8)
* [Dynamic Theming in Browser using Ant Design](https://medium.com/@mzohaib.qc/ant-design-dynamic-runtime-theme-1f9a1a030ba0)
* [Zero config custom theme generator](https://www.npmjs.com/package/@emeks/antd-custom-theme-generator)
* [ ](https://github.com/afc163)





## Replace Moment.js

* [Custom component](https://ant.design/docs/react/replace-moment#Custom-component)
* [antd-dayjs-webpack-plugin](https://ant.design/docs/react/replace-moment#antd-dayjs-webpack-plugin)
* [Use date-fns](https://ant.design/docs/react/replace-moment#Use-date-fns)

You might want to replace Moment.js with another date library \(**Ant design currently supports** [**dayjs**](https://day.js.org/) **and** [**date-fns**](https://date-fns.org/)\) to reduce bundle size. We provide two ways to customize:

### Custom component[\#](https://ant.design/docs/react/replace-moment#Custom-component) <a id="Custom-component"></a>

The first way is to use `generatePicker` \(or `generateCalendar`\) to help create Picker components.

First, we initialize an antd demo with `create-react-app`. You can refer to [Use in TypeScript](https://ant.design/docs/react/use-in-typescript), or you can start directly here [init antd](https://github.com/xiaohuoni/antd4-generate-picker/commit/47fec964e36d48bd15760f8f5abcb9655c259aa6)

#### DatePicker.tsx[\#](https://ant.design/docs/react/replace-moment#DatePicker.tsx) <a id="DatePicker.tsx"></a>

Create `src/components/DatePicker.tsx`.

For example:

```text
import { Dayjs } from 'dayjs';
import dayjsGenerateConfig from 'rc-picker/lib/generate/dayjs';
import generatePicker from 'antd/es/date-picker/generatePicker';
import 'antd/es/date-picker/style/index';

const DatePicker = generatePicker<Dayjs>(dayjsGenerateConfig);

export default DatePicker;
```

#### TimePicker.tsx[\#](https://ant.design/docs/react/replace-moment#TimePicker.tsx) <a id="TimePicker.tsx"></a>

Create `src/components/TimePicker.tsx`.

For example:

```text
import { Dayjs } from 'dayjs';
import * as React from 'react';
import DatePicker from './DatePicker';
import { PickerTimeProps } from 'antd/es/date-picker/generatePicker';

export interface TimePickerProps extends Omit<PickerTimeProps<Dayjs>, 'picker'> {}

const TimePicker = React.forwardRef<any, TimePickerProps>((props, ref) => {
  return <DatePicker {...props} picker="time" mode={undefined} ref={ref} />;
});

TimePicker.displayName = 'TimePicker';

export default TimePicker;
```

#### Calendar.tsx[\#](https://ant.design/docs/react/replace-moment#Calendar.tsx) <a id="Calendar.tsx"></a>

Create `src/components/Calendar.tsx`.

For example:

```text
import { Dayjs } from 'dayjs';
import dayjsGenerateConfig from 'rc-picker/lib/generate/dayjs';
import generateCalendar from 'antd/es/calendar/generateCalendar';
import 'antd/es/calendar/style';

const Calendar = generateCalendar<Dayjs>(dayjsGenerateConfig);

export default Calendar;
```

#### Export Custom component[\#](https://ant.design/docs/react/replace-moment#Export-Custom-component) <a id="Export-Custom-component"></a>

Create `src/components/index.tsx`.

For example:

```text
export { default as DatePicker } from './DatePicker';
export { default as Calendar } from './Calendar';
export { default as TimePicker } from './TimePicker';
```

#### Use Custom component[\#](https://ant.design/docs/react/replace-moment#Use-Custom-component) <a id="Use-Custom-component"></a>

Modify `src/App.tsx`,import `dayjs` and custom component.

```text
- import { DatePicker, Calendar } from 'antd';
- import format from 'moment';

+ import { DatePicker, TimePicker, Calendar } from './components';
+ import format from 'dayjs';
```

If the above steps do not work correctly, you can refer to [antd4-generate-picker/antd-ts](https://github.com/xiaohuoni/antd4-generate-picker/tree/master/antd-ts).

If you need JavaScript code, you can refer to [antd4-generate-picker/antd-demo](https://github.com/xiaohuoni/antd4-generate-picker/tree/master/antd-demo).

If you use [umi](https://umijs.org/), you can reference [antd4-use-dayjs-replace-moment](https://github.com/xiaohuoni/antd4-use-dayjs-replace-moment).

### antd-dayjs-webpack-plugin[\#](https://ant.design/docs/react/replace-moment#antd-dayjs-webpack-plugin) <a id="antd-dayjs-webpack-plugin"></a>

We also provide another implementation, which we provide with `antd-dayjs-webpack-plugin`, replacing `momentjs` with `Day.js` directly without changing a line of existing code. More info can be found at [antd-dayjs-webpack-plugin](https://github.com/ant-design/antd-dayjs-webpack-plugin).

```text
// webpack-config.js
import AntdDayjsWebpackPlugin from 'antd-dayjs-webpack-plugin';

module.exports = {
  // ...
  plugins: [new AntdDayjsWebpackPlugin()],
};
```

### Use date-fns[\#](https://ant.design/docs/react/replace-moment#Use-date-fns) <a id="Use-date-fns"></a>

[date-fns](https://date-fns.org/) currently supports custom component methods similar to `dayjs`. The difference is that the parameter types used are different. Support is provided in antd 4.5.0 and above.

For Example:

#### DatePicker.tsx[\#](https://ant.design/docs/react/replace-moment#DatePicker.tsx) <a id="DatePicker.tsx"></a>

Create `src/components/DatePicker.tsx`.

Code as follows:

```text
import dateFnsGenerateConfig from 'rc-picker/lib/generate/dateFns';
import generatePicker from 'antd/es/date-picker/generatePicker';
import 'antd/es/date-picker/style/index';

const DatePicker = generatePicker<Date>(dateFnsGenerateConfig);

export default DatePicker;
```

* [ ](https://github.com/afc163)







