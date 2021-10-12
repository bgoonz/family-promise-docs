# Ant Design

{% embed url="https://youtu.be/y8CJt19mgXo" %}



##  <a href="9e25" id="9e25"></a>

## How to implement ANT Design with React <a href="9e25" id="9e25"></a>



_Following the Ant Design specification, we developed a React UI library `antd` that contains a set of high quality components and demos for building rich, interactive user interfaces._

_✨ Features_

🌈 Enterprise-class UI designed for web applications.

📦 A set of high-quality React components out of the box.

🛡 Written in TypeScript with predictable static types.

⚙️ Whole package of design resources and development tools.

🌍 Internationalization support for dozens of languages.

🎨 Powerful theme customization in every detail.

_Source: _[_Ant Design_](https://ant.design/docs/react/introduce)

I have found ANT Design as the smart option to design our web applications using react. It provides us high quality components which we will be observing while developing the project, in the article later on. If you look around to the documentation provided by ANT and observe its demo of different features, you will find ANT as the better option for you application. So we will be developing a simple react application using following ANT Components. So, let’s start!

### ANT Components <a href="a77d" id="a77d"></a>

There are a lot of beautiful and useful components provided by ANT Design. But I will brief you about some of the basic components that we will be using to built a system with React and ANT in this article.

**1. Layout**\
Layout is basically a wrapper, which consist of Header, Footer, Sider, Content and layout itself. You can modify plenty of things for your layout. Please refer to [layout documentation](https://ant.design/components/layout/) of ANT for more.![](https://miro.medium.com/max/30/1\*pz9xc4Vuac5z-Ls4RKaQIQ.png?q=20)![](https://miro.medium.com/max/709/1\*pz9xc4Vuac5z-Ls4RKaQIQ.png)Layout given by ANT

**2. Grid**\
ANT Design is a 24 Grid System.The column Grid system in ANT Design is a value of 1–24 to represent its range spans. You can use Row for rows and Col for columns and you can have 24 columns in a row. You can define a col span lik \<Col span={8}> for columns of three equal widths. Learn more [here](https://ant.design/components/grid/).![](https://miro.medium.com/max/30/1\*IgBiC1XYroEAOrRWKJwaLg.png?q=20)![](https://miro.medium.com/max/709/1\*IgBiC1XYroEAOrRWKJwaLg.png)Grid system of ANT

**3. Form**\
ANT provides high performance Form Component with data scope management which includes data collection, verification and styles. Learn more about forms [here](https://ant.design/components/form/).

**4. Input**\
It is a basic widget for getting the user input as a text field. You can use input group, text area, format tooltip input and many more from input. Learn more [here](https://ant.design/components/input/).

**5. Radio**\
Radio is used to select a single state from multiple options. You can check out different use cases of Radio in Ant from [here](https://ant.design/components/radio/).

**6. Switch**\
If you need to have switching between two states that is on-off state you can use Switch. I was really impressed with the pending state implemented in switch by ANT. For knowing more about it, please refer the document [here](https://ant.design/components/switch/).

**7. Slider**\
Slider component is used for displaying current value or the range of the value. ANT provides the better component for using Slider. Learn more [here](https://ant.design/components/slider/).

**8. Select**\
Select component allows us to select a value or set of values from the options available to us. There are many use cases of the select component defined by ANT. Learn more [here](https://ant.design/components/select/).

**9. Message**\
We use message as the feedback in response to the operations performed by the user. We use message component for displaying feedback such as success, error, warning, etc. Message is displayed at top-center and will be dismissed automatically. Learn more [here](https://ant.design/components/message/).

**10. Table**\
****We can use Table to display a collection of structured data in rows. We can define dataSource and columns to display rows data and columns of the table. Learn more [here](https://ant.design/components/table/#header).

**11. Empty**\
You can use this component when there is nothing to display in your page or your component. I gives good User Experience as well. Learn more about Empty [here](https://ant.design/components/empty/).![](https://miro.medium.com/max/30/1\*VYtKX\_1QzcszNycjldry5A.png?q=20)![](https://miro.medium.com/max/709/1\*VYtKX\_1QzcszNycjldry5A.png)ANT Empty Component

### Create React App <a href="2c1c" id="2c1c"></a>

We somewhat touched the basic components we will be using now. So, now let’s create a new react project named **react-ant **with typescript.

```
npx create-react-app react-ant --template typescript
cd react-antnpm install --save typescript @types/node @types/react @types/react-dom @types/jest
```

### Install React Router <a href="594c" id="594c"></a>

We will be using _React Router_ to navigate to different pages of the application.\
Let’s install them as well.

```
npm install --save react-router-dom
npm install @types/react-router
```

### Install ANT Design <a href="0b5d" id="0b5d"></a>

So, finally we install _ANT Design_ to our system with following command.

```
npm install antd
```

Also import antd css to the index file, _index.tsx_.

```
//src/index.tsximport 'antd/dist/antd.css';
```

### Create Fake Json Server <a href="4b91" id="4b91"></a>

We will be using the Fake Json Server for storing and retrieving our data locally. I am using it because our application is small and we will be storing and retrieving the data later on. Install Json Server with following command.

```
npm install -g json-server
```

Create a folder named _Server _and create a file named _db.json _to record our data. We create a users collection in db.json which will be holding our users data later on.

```
{
 "users": []
}
```

Next thing you need to do is to create _json-server.json_ file to the root of the project and it will hold port for our server.

```
{ 
"port": 5000
}
```

For running the json server you run following command on your terminal. Keep your server running.

```
json-server --watch server/db.json
```

### Install Axios <a href="e9aa" id="e9aa"></a>

Axios is the promise based HTTP client for the browser and node.js. We will be using Axios as well in the application. So, lets’s install it.

```
npm install --save axios
```

### Create Layout <a href="5e4b" id="5e4b"></a>

Now we start structuring our application with files and folder. First of all we will create two folders inside _src_ and give them the name _components_ and _config_ respectively. We will add route configuration and layout in config folder and different pages and layouts in components folder. For your easiness, I am going to provide the screen shot of files and folder that we are going to create.![](https://miro.medium.com/max/30/1\*s5DGrVxqCnj7z2SBTefT0A.png?q=20)![](https://miro.medium.com/max/641/1\*s5DGrVxqCnj7z2SBTefT0A.png)Project Structure of REACT-ANT

Also delete the unnecessary files and logos that we will not be using from the project. So, now we will start our code with** App.tsx**.

```
// src/App.tsximport React from 'react';
import ApplicationRoutes from "./config/ApplicationRoutes";function App() {
  return (
    <ApplicationRoutes />
  );
}export default App;
```

Now we define our route for different pages and we define our layout on the ApplicationRoutes.tsx file. I have added all the routes, but you can add those routes after adding those components for not getting error. I have also added the header component and content here and grabbed the sider component form layout. You can separate them as well, if you want cleaner code.

```
//src/config/ApplicationRoutes.tsximport React, {useState, useEffect} from 'react';
import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";
import List from "../components/pages/list";
import Form from "../components/pages/form";
import SideNav from "../components/layouts/sidebar";
import File from "../components/pages/files";
import Videos from "../components/pages/videos";import { Layout } from 'antd';
import {
    MenuUnfoldOutlined,
    MenuFoldOutlined
  } from '@ant-design/icons';const { Header, Sider, Content} = Layout;const ApplicationRoutes = () => {
  const [collapse, setCollapse] = useState(false);useEffect(() => {
    window.innerWidth <= 760 ? setCollapse(true) : setCollapse(false);
  }, []);const handleToggle = (event: any) => {
        event.preventDefault();
        collapse ? setCollapse(false) : setCollapse(true);
    }
  return (
      <Router>
        <Layout>
          <Sider trigger={null} collapsible collapsed={collapse}>
            <SideNav />
          </Sider>
          <Layout>
            <Header className="siteLayoutBackground" style={{padding: 0, background: "#001529"}}>
                      {React.createElement(collapse ? MenuUnfoldOutlined : MenuFoldOutlined, {
                          className: 'trigger',
                          onClick: handleToggle,
                          style: {color: "#fff"}
                      })}
            </Header>
              <Content style={{margin: '24px 16px', padding: 24, minHeight: "calc(100vh - 114px)", background: "#fff"}}>
                <Switch>
                    <Route path="/list" component={List} />
                    <Route path="/form" component={Form} />
                    <Route path="/files" component={File} />
                    <Route path="/videos" component={Videos} />
                    <Redirect to="/list" from="/" />
                </Switch>
              </Content>
          </Layout>
        </Layout>
    </Router>
  );
}export default ApplicationRoutes;
```

We have imported SideNav from sidebar.tsx, so we add that immediately. For that create a file named _sidebar.tsx_ inside _layouts_ folder in _components_ directory. We define menu and menu items for the sidebar and we use the awesome icons provided by Ant.

```
import React from 'react';
import { Menu } from 'antd';
import {
    UserOutlined,
    VideoCameraOutlined,
    UploadOutlined,
  } from '@ant-design/icons';
import {useHistory}  from 'react-router';const SideNav = () => {
    const history = useHistory();const handleUserClick = () => {
        history.push('/list');
    }const handleVideosClick = () => {
        history.push('/videos');
    }const handleFileClick = () => {
        history.push('/files');
    }return (
      <div>
        <div style={{height: "32px", background: "rgba(255, 255, 255, 0.2)", margin: "16px"}}></div>
            <Menu theme="dark" mode="inline" defaultSelectedKeys={['1']}>
                <Menu.Item key="1" onClick={handleUserClick}>
                    <UserOutlined />
                    <span> Users</span>
                </Menu.Item>
                <Menu.Item key="2" onClick={handleVideosClick}>
                    <VideoCameraOutlined />
                    <span> Videos</span>
                </Menu.Item>
                <Menu.Item key="3" onClick={handleFileClick}>
                    <UploadOutlined />
                    <span> Files</span>
                </Menu.Item>
            </Menu>
        </div>
  );
}export default SideNav;
```

Now the missing part is our list page and the form, so we work to complete them.

### Create List <a href="146a" id="146a"></a>

We are using table to display list of user data entered by the user. We define columns and data for the table. Moreover, we add a button to navigate to the Form to fill it up and add in the table. We grab the data from our json server using axios. So let’s see how our table is going to look like.

```
//src/components/pages/list.tsximport React, {useEffect, useState} from 'react';
import {Table, Row, Col, Button, Typography} from 'antd';
import {useHistory} from 'react-router';
import axios from 'axios';const {Title} = Typography;const List = () => {
  const history = useHistory();
  const [allData, setAllData] = useState([]);useEffect(() => {
    axios.get(`http://localhost:5000/users`).then(res => {
      setAllData(res.data);
    });
  }, []);const columns = [
    {
      title: 'Username',
      dataIndex: 'username',
    },
    {
      title: 'Email',
      dataIndex: 'email'
    },
    {
      title: 'Gender',
      dataIndex: 'gender'
    },
    {
      title: 'Review',
      dataIndex: 'review'
    },
  ];const data = [{
  }];allData.map((user: any) => {
    data.push({
     key: user.id,
     username: user.username,
     email: user.email,
     gender: user.gender,
     review: user.review + '%',
   })
   return data;
 });const handleClick = () => {
    history.push('/form')
  }return (
    <div>
        <Row gutter={[40, 0]}>
          <Col span={18}>
            <Title level={2}>
            User List
            </Title>
            </Col>
          <Col span={6}>
          <Button onClick={handleClick} block>Add User</Button>
          </Col>
        </Row>
        <Row gutter={[40, 0]}>
        <Col span={24}>
        <Table columns={columns} dataSource={data} />
        </Col>
        </Row>
    </div>
  );
}export default List;
```

### **Create Form** <a href="1152" id="1152"></a>

We are going to implement a lot of above mentioned components to design our form and obviously, we will be using json server to store the user data. We have applied basic validation for our form as well. Moreover, you can look at the code and get known to various components and their interaction in the system. So let’s create our form.

```
//src/components/pages/form.tsximport React, {useState} from 'react';
import {Row, Col, Typography, Input, Form, Button, 
Radio, Switch, Slider, Select, message} from 'antd';
import axios from 'axios';
import {useHistory} from 'react-router';const {Title} = Typography;const layout = {
  labelCol: { span: 8 },
  wrapperCol: { span: 16 },
};const FormApp = () => {
  const [loading, setLoading] = useState(false);
  const history = useHistory();const handleSubmit = (values: any) => {
    setLoading(true);
    axios.post(`http://localhost:5000/users`, 
      values
    )
    .then(res => {
      setLoading(false);
      message.success('User Added Successfully!');
      history.push('/list');
    })
    .catch(error => {
      setLoading(false);
      message.error(error);
    })
  }return (
    <div>
        <Row gutter={[40, 0]}>
          <Col span={23}>
            <Title style={{textAlign: 'center'}} level={2}>
            Please Fill the User Form
            </Title>
            </Col>
        </Row>
        <Row gutter={[40, 0]}>
        <Col span={18}>
          <Form {...layout} onFinish={handleSubmit}>
            <Form.Item name="username" label="UserName"
            rules={[
              {
                required: true,
                message: 'Please input your name',
              }
            ]}
            >
              <Input placeholder="Please Enter your username" />
            </Form.Item>
            <Form.Item name="email" label="Email" 
            rules={[
              {
                required: true,
                message: 'Please input your correct email',
                type: 'email'
              }
            ]}
            >
              <Input placeholder="Please Enter your email" />
            </Form.Item>
            <Form.Item name="gender" label="Gender" 
            rules={[
              {
                required: true,
                message: 'Please select your gender',
              }
            ]}
            >
              <Radio.Group>
                <Radio value="male">Male</Radio>
                <Radio value="female">Female</Radio>
                <Radio value="others">Others</Radio>
              </Radio.Group>
            </Form.Item>
            <Form.Item name="hobbies" label="Hobbies" 
            rules={[
              {
                required: true,
                message: 'Please select your hobbies',
                type: 'array'
              }
            ]}
            >
              <Select mode="multiple" placeholder="Please select you hobbies">
                <Select.Option value="Reading">Reading</Select.Option>
                <Select.Option value="Writing">Writing</Select.Option>
                <Select.Option value="Coding">Coding</Select.Option>
                <Select.Option value="Singing">Singing</Select.Option>
                <Select.Option value="Dancing">Dancing</Select.Option>
              </Select>
            </Form.Item>
            <Form.Item name="review" label="Review"
            >
              <Slider />
            </Form.Item>
            <Form.Item name="notificaiton" label="Notificaiton" valuePropName="checked"
            >
              <Switch />
            </Form.Item>
            <div style={{textAlign: "right"}}>
            <Button type="primary" loading={loading} htmlType="submit">
              Save
            </Button>{' '}
            <Button type="danger" htmlType="button" onClick={() => history.push('/list')}>
              Back
            </Button>
              </div>
          </Form>
          </Col>
        </Row>
    </div>
  );
}export default FormApp;
```

For using the _Empty _component,_ _we will be adding two more pages _files.tsx _and _videos.tsx_ with no data. You can implement Empty component as given below.

```
//src/components/pages/videos.tsximport React from 'react';
import {Empty} from 'antd';const Videos = () => {
  return (
    <div>
        <Empty />
    </div>
  );
}export default Videos;
```

Also the files page looks like.

```
//src/components/pages/files.tsximport React from 'react';
import {Empty} from 'antd';const Files = () => {
  return (
    <div>
        <Empty />
    </div>
  );
}export default Files;
```

### Demo <a href="cc53" id="cc53"></a>

For checking our system to perform as expected, please make sure that our Front end and Server is running properly. Run react project with following command if you haven’t done yet.

```
npm start
```

Also make sure our json server is working perfectly.

```
json-server --watch server/db.json
```

Boom! You will get the empty user list with a beautiful layout and bunch of menus on the sidebar. It looks cool!![](https://miro.medium.com/max/30/1\*eYWIrq3o3UssNPe1o0oAgw.png?q=20)![](https://miro.medium.com/max/709/1\*eYWIrq3o3UssNPe1o0oAgw.png)Empty Table

Navigate to Add user and you will get this user form. It looks more cool!![](https://miro.medium.com/max/30/1\*NdReF_IeD0jaAbByJSykng.png?q=20)![](https://miro.medium.com/max/709/1\*NdReF_IeD0jaAbByJSykng.png)User Form

Now fill up all the fields and click save or click back to navigate to the list page. You will see the loading on save button until the form gets submitted. Lets see how it looks like.![](https://miro.medium.com/max/30/1\*tJZfdtGELSDAx10NVnWZew.png?q=20)![](https://miro.medium.com/max/709/1\*tJZfdtGELSDAx10NVnWZew.png)New user added with a success message

This is how you can add new users and let’s see our empty components by navigating to videos from left menu.![](https://miro.medium.com/max/30/1\*xNy_OTTUEdUeBDdIlJ7uTg.png?q=20)![](https://miro.medium.com/max/709/1\*xNy_OTTUEdUeBDdIlJ7uTg.png)Video page with no data

We implemented some of the basic components of Ant Design with React. There are a lot more components and designs provided by Ant. It is so easy to use and much efficient for the user experience. You can add more attributes to the application we developed just now, using other Ant Components. You can refer to my github link of the project for any confusions or you can write it down on the comments below as well. I will be covering more parts of ANT Design in upcoming articles too.\
Stay Tuned!

**Github:** [https://github.com/SudeepTimalsina/ReactAnt](https://github.com/SudeepTimalsina/ReactAnt)

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

### ✨ Features[#](https://ant.design/docs/react/introduce#%E2%9C%A8-Features) <a href="features" id="features"></a>

* 🌈 Enterprise-class UI designed for web applications.
* 📦 A set of high-quality React components out of the box.
* 🛡 Written in TypeScript with predictable static types.
* ⚙️ Whole package of design resources and development tools.
* 🌍 Internationalization support for dozens of languages.
* 🎨 Powerful theme customization in every detail.

### Environment Support[#](https://ant.design/docs/react/introduce#Environment-Support) <a href="environment-support" id="environment-support"></a>

* Modern browsers and Internet Explorer 11 (with [polyfills](https://ant.design/docs/react/getting-started#Compatibility))
* Server-side Rendering
* [Electron](https://www.electronjs.org)

| <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge"></a><br>IE / Edge</p> | <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox"></a><br>Firefox</p> | <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome"></a><br>Chrome</p> | <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari"></a><br>Safari</p> | <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera"></a><br>Opera</p> | <p><a href="http://godban.github.io/browsers-support-badges/"><img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/electron/electron_48x48.png" alt="Electron"></a><br>Electron</p> |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IE11, Edge                                                                                                                                                                                          | last 2 versions                                                                                                                                                                                       | last 2 versions                                                                                                                                                                                   | last 2 versions                                                                                                                                                                                   | last 2 versions                                                                                                                                                                               | last 2 versions                                                                                                                                                                                           |

Polyfills are needed for IE browsers. We recommend [@babel/preset-env](https://babeljs.io/docs/en/babel-preset-env) for it. You can set `targets` config if you are using [umi](http://umijs.org).

> We drop support of IE8 after `antd@2.0`, We drop support of React 15 and IE9/10 after `antd@4.0`,

### Version[#](https://ant.design/docs/react/introduce#Version) <a href="version" id="version"></a>

* Stable: [![npm package](https://img.shields.io/npm/v/antd.svg?style=flat-square)](https://www.npmjs.org/package/antd)

You can subscribe to this feed for new version notifications: [https://github.com/ant-design/ant-design/releases.atom](https://github.com/ant-design/ant-design/releases.atom)

### Installation[#](https://ant.design/docs/react/introduce#Installation) <a href="installation" id="installation"></a>

#### Using npm or yarn[#](https://ant.design/docs/react/introduce#Using-npm-or-yarn) <a href="using-npm-or-yarn" id="using-npm-or-yarn"></a>

**We recommend using npm or yarn to install**, it not only makes development easier, but also allow you to take advantage of the rich ecosystem of Javascript packages and tooling.

```
$ npm install antd
```

```
$ yarn add antd
```

If you are in a bad network environment, you can try other registries and tools like [cnpm](https://github.com/cnpm/cnpm).

#### Import in Browser[#](https://ant.design/docs/react/introduce#Import-in-Browser) <a href="import-in-browser" id="import-in-browser"></a>

Add `script` and `link` tags in your browser and use the global variable `antd`.

We provide `antd.js` `antd.css` and `antd.min.js` `antd.min.css` under `antd/dist` in antd's npm package. You can also download these files directly from [![CDNJS](https://img.shields.io/cdnjs/v/antd.svg?style=flat-square)](https://cdnjs.com/libraries/antd), [![](https://data.jsdelivr.com/v1/package/npm/antd/badge)](https://www.jsdelivr.com/package/npm/antd) or [unpkg](https://unpkg.com/antd/dist).

> **We strongly discourage loading the entire files** this will add bloat to your application and make it more difficult to receive bugfixes and updates. Antd is intended to be used in conjunction with a build tool, such as [webpack](https://webpack.github.io), which will make it easy to import only the parts of antd that you are using.
>
> Note: you should import react/react-dom/moment before using antd.js.

### Usage[#](https://ant.design/docs/react/introduce#Usage) <a href="usage" id="usage"></a>

```
import { DatePicker } from 'antd';

ReactDOM.render(<DatePicker />, mountNode);
```

And import stylesheets manually:

```
import 'antd/dist/antd.css'; // or 'antd/dist/antd.less'
```

#### Use modularized antd[#](https://ant.design/docs/react/introduce#Use-modularized-antd) <a href="use-modularized-antd" id="use-modularized-antd"></a>

`antd` supports ES modules tree shaking by default for JS part.

#### TypeScript[#](https://ant.design/docs/react/introduce#TypeScript) <a href="typescript" id="typescript"></a>

`antd` provides a built-in ts definition, don't install `@types/antd`.

### Links[#](https://ant.design/docs/react/introduce#Links) <a href="links" id="links"></a>

* [Home page](https://ant.design)
* [Components](https://ant.design/components/overview/)
* [Ant Design Pro](https://pro.ant.design)
* [Ant Design Charts](https://charts.ant.design)
* [Change Log](https://ant.design/changelog)
* [rc-components](http://react-component.github.io)
* [Mobile UI](http://mobile.ant.design)
* [Ant Design Icons](https://github.com/ant-design/ant-design-icons)
* [Ant Design Colors](https://github.com/ant-design/ant-design-colors)
* [Ant Design Pro Layout](https://github.com/ant-design/ant-design-pro-layout)
* [Ant Design Pro Blocks](https://github.com/ant-design/pro-blocks)
* [Dark Theme](https://github.com/ant-design/ant-design-dark-theme)
* [Landing Pages](https://landing.ant.design)
* [Motion](https://motion.ant.design)
* [Scaffold Market](http://scaffold.ant.design)
* [Developer Instruction](https://github.com/ant-design/ant-design/wiki/Development)
* [Versioning Release Note](https://github.com/ant-design/ant-design/wiki/%E8%BD%AE%E5%80%BC%E8%A7%84%E5%88%99%E5%92%8C%E7%89%88%E6%9C%AC%E5%8F%91%E5%B8%83%E6%B5%81%E7%A8%8B)
* [FAQ](https://ant.design/docs/react/faq)
* [CodeSandbox Template](https://u.ant.design/codesandbox-repro) for bug reports
* [Awesome Ant Design](https://github.com/websemantics/awesome-ant-design)
* [Customize Theme](https://ant.design/docs/react/customize-theme)
* [How to Apply for Being A Collaborator](https://github.com/ant-design/ant-design/wiki/Collaborators#how-to-apply-for-being-a-collaborator)





## Getting Started

Ant Design React is dedicated to providing a **good development experience** for programmers. Before starting, it is recommended to learn [React](https://reactjs.org) and [ES2015](http://babeljs.io/docs/learn-es2015/) first, and correctly install and configure [Node.js](https://nodejs.org) v8 or above.

The official guide also assumes that you have intermediate knowledge about HTML, CSS, and JavaScript, and React. If you are just starting to learn front-end or React, it may not be the best idea to use the UI framework as your first step.

Finally, if you are working in a local development environment, please refer to [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) section of "Use in create-react-app".

* [Your First Example](https://ant.design/docs/react/getting-started#Your-First-Example)
* [Test with Jest](https://ant.design/docs/react/getting-started#Test-with-Jest)
* [Import on Demand](https://ant.design/docs/react/getting-started#Import-on-Demand)
* [Customize your Workflow](https://ant.design/docs/react/getting-started#Customize-your-Workflow)

### Your First Example[#](https://ant.design/docs/react/getting-started#Your-First-Example) <a href="your-first-example" id="your-first-example"></a>

Here is a simple online codesandbox demo of an Ant Design component to show the usage of Ant Design React.

Follow the steps below to play around with Ant Design yourself:

#### 1. Create a codesandbox[#](https://ant.design/docs/react/getting-started#1.-Create-a-codesandbox) <a href="1.-create-a-codesandbox" id="1.-create-a-codesandbox"></a>

Visit [http://u.ant.design/codesandbox-repro](http://u.ant.design/codesandbox-repro) to create a codesandbox -- don't forget to press the save button as well to create a new instance.

#### 2. Use and modify an antd component[#](https://ant.design/docs/react/getting-started#2.-Use-and-modify-an-antd-component) <a href="2.-use-and-modify-an-antd-component" id="2.-use-and-modify-an-antd-component"></a>

Replace the contents of `index.js` with the following code. As you can see, there is no difference between antd's components and typical React components.

If you have already set things up by following the [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) section of "Use in create-react-app", replace the content of `/src/index.js` as follows:

```
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

#### 3. Explore more components[#](https://ant.design/docs/react/getting-started#3.-Explore-more-components) <a href="3.-explore-more-components" id="3.-explore-more-components"></a>

You can view the list of components in the side menu of the Components page, such as the [Alert](https://ant.design/components/alert/) component. Plenty of examples are also provided in the component pages and API documentation as well.

Click the "Open in Editor" icon in the first example to open an editor with source code to use out-of-the-box. Now you can import the `Alert` component into the codesandbox:

```
- import { DatePicker, message } from 'antd';
+ import { DatePicker, message, Alert } from 'antd';
```

Now add the following jsx inside the `render` function.

```
  <DatePicker onChange={value => this.handleChange(value)} />
  <div style={{ marginTop: 20 }}>
-   Selected Date: {date ? date.format('YYYY-MM-DD') : 'None'}
+   <Alert message="Selected Date" description={date ? date.format('YYYY-MM-DD') : 'None'} />
  </div>
```

Select a date, and you can see the effect in the preview area on the right:

![codesandbox screenshot](https://gw.alipayobjects.com/zos/antfincdn/JrXptUm1Nz/6b50edc4-3a3c-4b2a-843e-f9f0af2c4667.png)

OK! Now that you know the basics of using antd components, you are welcome to explore more components in the codesandbox. When reporting a bug with ant design, we also strongly recommend using codesandbox to provide a reproducible demo as well.

#### 4. Next Steps[#](https://ant.design/docs/react/getting-started#4.-Next-Steps) <a href="4.-next-steps" id="4.-next-steps"></a>

During actual real-world project development, you will most likely need a development workflow consisting of `compile/build/deploy/lint/debug/` deployment. You can read the following documents on the subject or use the following scaffolds and examples provided below:

* [Ant Design Pro](http://pro.ant.design)
* [antd-admin](https://github.com/zuiidea/antd-admin)
* [d2-admin](https://github.com/d2-projects/d2-admin)
* More scaffolds at [Scaffold Market](http://scaffold.ant.design)

### Test with Jest[#](https://ant.design/docs/react/getting-started#Test-with-Jest) <a href="test-with-jest" id="test-with-jest"></a>

If you use `create-react-app` follow the instructions [here](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest) instead.

Jest does not support `esm` modules, and Ant Design uses them. In order to test your Ant Design application with Jest you have to add the following to your Jest config :

```
"transform": { "^.+\\.(ts|tsx|js|jsx)?$": "ts-jest" }
```

### Import on Demand[#](https://ant.design/docs/react/getting-started#Import-on-Demand) <a href="import-on-demand" id="import-on-demand"></a>

`antd` supports tree shaking of ES modules, so using `import { Button } from 'antd';` would drop js code you didn't use.

If you see logs like in the screenshot below, you might still be using `webpack@1.x` or have a wrong webpack config which can't support tree shaking.

```
You are using a whole package of antd, please use https://www.npmjs.com/package/babel-plugin-import to reduce app bundle size. Please upgrade webpack or check the config.
```

> ![console warning](https://zos.alipayobjects.com/rmsportal/GHIRszVcmjccgZRakJDQ.png)

### Customize your Workflow[#](https://ant.design/docs/react/getting-started#Customize-your-Workflow) <a href="customize-your-workflow" id="customize-your-workflow"></a>

If you want to customize your workflow, we recommend using [webpack](http://webpack.github.io) to build and debug code. You can try out plenty of [boilerplates](https://github.com/enaqx/awesome-react#react-tools) available in the React ecosystem.

There are also some [scaffolds](http://scaffold.ant.design) which have already been integrated into antd, so you can try and start with one of these and even contribute.



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

And [umi](https://umijs.org) is a routing-based framework that supports [next.js-like conventional routing](https://umijs.org/docs/convention-routing) and various advanced routing functions, such as [routing-level on-demand loading](https://umijs.org/config#dynamicimport). With a complete [plugin system](https://umijs.org/plugins/api) that covers every life cycle from source code to build product, umi is able to support various functional extensions and business needs; meanwhile [Umi UI](https://umijs.org/docs/use-umi-ui) is provided to enhance the development experience and development efficiency through Visual Aided Programming (VAP).

> You may also be interested in [Ant Design Pro](https://pro.ant.design), an Out-of-box UI solution for enterprise applications based on umi, dva and ant design.

This article will guide you to create a simple application from zero using Umi, dva and antd.

### Install Umi[#](https://ant.design/docs/react/practical-projects#Install-Umi) <a href="install-umi" id="install-umi"></a>

It is recommended to use yarn to create an application and execute the following command.

```
$ mkdir myapp && cd myapp
$ yarn create @umijs/umi-app
$ yarn
```

> If you use npm, you can execute `npx @umijs/create-umi-app` with the same effect.
>
> And if you want to use a fixed version of antd, you can install additional antd dependency in your project, and the antd dependencies declared in package.json will be used first.

### Create Routes[#](https://ant.design/docs/react/practical-projects#Create-Routes) <a href="create-routes" id="create-routes"></a>

We need to write an application displaying the list of products. The first step is to create a route.

If you don't have npx, you need to install it first to execute the commands under node_modules.

```
$ yarn global add npx
```

Then create a `/products` route,

```
$ npx umi g page products --typescript

Write: src/pages/products.tsx
Write: src/pages/products.css
```

In `.umirc.ts` configured in routing, if there is need to internationalization, can configure `locale` enable antd internationalization:

```
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

### Write UI Components[#](https://ant.design/docs/react/practical-projects#Write-UI-Components) <a href="write-ui-components" id="write-ui-components"></a>

As your application grows and you notice you are sharing UI elements between multiple pages (or using them multiple times on the same page), in umi it's called reusable components.

Let's create a `ProductList` component that we can use in multiple places to show a list of products.

Create `src/components/ProductList.tsx` by typing:

```
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

### Simple data management solution[#](https://ant.design/docs/react/practical-projects#Simple-data-management-solution) <a href="simple-data-management-solution" id="simple-data-management-solution"></a>

`@umijs/plugin-model` is a simple data flow scheme based on the hooks paradigm, which can replace dva to perform global data flow in the middle stage under certain circumstances. We agree that the files in the `src/models` directory are the model files defined by the project. Each file needs to export a function by default, the function defines a hook, and files that do not meet the specifications will be filtered out.

The file name corresponds to the name of the final model, and you can consume the data in the model through the API provided by the plug-in.

Let's take a simple table as an example. First you need to create a new file `src/models/useProductList.ts`.

```
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

```
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

### ProLayout[#](https://ant.design/docs/react/practical-projects#ProLayout) <a href="prolayout" id="prolayout"></a>

A standard mid-to-back page generally requires a layout. This layout is often highly similar. ProLayout encapsulates commonly used menus, breadcrumbs, page headers and other functions, provides an independent framework and works out of the box Advanced layout components.

And supports three modes of `side`, `mix`, and `top`, and it also has built-in menu selection, the menu generates breadcrumbs, and automatically sets the logic of the page title. Can help you start a project quickly.

![site](https://gw.alipayobjects.com/zos/antfincdn/gXkuc%26RmT7/64038246-E2BF-4840-8898-5AF531897A44.png)

The method of use is also extremely simple, requiring only a few simple settings.

```
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

### ProTable[#](https://ant.design/docs/react/practical-projects#ProTable) <a href="protable" id="protable"></a>

Many data in an admin page does not need to be shared across pages, and models are sometimes not needed.

```
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

### Build[#](https://ant.design/docs/react/practical-projects#Build) <a href="build" id="build"></a>

Now that we've written our application and verified that it works in development, it's time to get it ready for deployment to our users. To do so, execute the following command:

```
$ yarn build
```

![](https://gw.alipayobjects.com/zos/antfincdn/Zd3f%242NdOK/b911d244-f1a5-4d61-adc5-3710cd86cd1b.png)

The `build` command packages up all of the assets that make up your application —— JavaScript, templates, CSS, web fonts, images, and more. Then you can find these files in the `dist/` directory.

### What's Next[#](https://ant.design/docs/react/practical-projects#What's-Next) <a href="whats-next" id="whats-next"></a>

We have completed a simple application, but you may still have lots of questions, such as:

* How to handle onError globally and locally?
* How to handle routes?
* How to mock data?
* How to deploy?
* ant so on...

You can:

* Visit [umi official website](https://umijs.org) and [dva official website](https://dvajs.com)
* Know [the umi routes](https://umijs.org/zh/guide/router.html)
* Know [how to deploy umi application](https://umijs.org/zh/guide/deploy.html)
* Scaffolding out of the box [Ant Design Pro](https://pro.ant.design)
* Advanced Layout [ProLayout](https://prolayout.ant.design)
* Advanced Table [ProTable](https://protable.ant.design)





## Use in create-react-app

[create-react-app](https://github.com/facebookincubator/create-react-app) is one of the best React application development tools. We are going to use `antd` within it and modify the webpack config for some customized needs.

* [Install and Initialization](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization)
* [Import antd](https://ant.design/docs/react/use-with-create-react-app#Import-antd)
* [Test with Jest](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest)
* [Advanced Guides](https://ant.design/docs/react/use-with-create-react-app#Advanced-Guides)
* [eject](https://ant.design/docs/react/use-with-create-react-app#eject)
* [Summary](https://ant.design/docs/react/use-with-create-react-app#Summary)

### Install and Initialization[#](https://ant.design/docs/react/use-with-create-react-app#Install-and-Initialization) <a href="install-and-initialization" id="install-and-initialization"></a>

Before all start, you may need install [yarn](https://github.com/yarnpkg/yarn/).

```
$ yarn create react-app antd-demo

# or

$ npx create-react-app antd-demo
```

The tool will create and initialize environment and dependencies automatically, please try config your proxy setting or use another npm registry if any network errors happen during it.

Then we go inside `antd-demo` and start it.

```
$ cd antd-demo
$ yarn start
```

Open the browser at [http://localhost:3000/](http://localhost:3000). It renders a header saying "Welcome to React" on the page.

### Import antd[#](https://ant.design/docs/react/use-with-create-react-app#Import-antd) <a href="import-antd" id="import-antd"></a>

Below is the default directory structure.

```
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

```
$ yarn add antd
```

Modify `src/App.js`, import Button component from `antd`.

```
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

```
@import '~antd/dist/antd.css';
```

Ok, you should now see a blue primary button displayed on the page. Next you can choose any components of `antd` to develop your application. Visit other workflows of `create-react-app` at its [User Guide](https://create-react-app.dev/docs/getting-started).

We are successfully running antd components now, go build your own application!

### Test with Jest[#](https://ant.design/docs/react/use-with-create-react-app#Test-with-Jest) <a href="test-with-jest" id="test-with-jest"></a>

`create-react-app` comes with `jest` built in. Jest does not support `esm` modules, and Ant Design uses them. In order to test your Ant Design application with Jest you have to add the following to your `package.json` :

```
"jest": {
  "transformIgnorePatterns": [
    "/node_modules/(?!antd|@ant-design|rc-.+?|@babel/runtime).+(js|jsx)$"
  ]
}
```

### Advanced Guides[#](https://ant.design/docs/react/use-with-create-react-app#Advanced-Guides) <a href="advanced-guides" id="advanced-guides"></a>

In the real world, we usually have to modify default webpack config for custom needs such as themes. We can achieve that by using [craco](https://github.com/gsoft-inc/craco) which is one of create-react-app's custom config solutions.

Install craco and modify the `scripts` field in `package.json`.

```
$ yarn add @craco/craco
```

```
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

```
/* craco.config.js */
module.exports = {
  // ...
};
```

#### Customize Theme[#](https://ant.design/docs/react/use-with-create-react-app#Customize-Theme) <a href="customize-theme" id="customize-theme"></a>

According to the [Customize Theme documentation](https://ant.design/docs/react/customize-theme), we need to modify less variables via loader like [less-loader](https://github.com/webpack/less-loader). We can use [craco-less](https://github.com/DocSpring/craco-less) to achieve that,

First we should modify `src/App.css` to `src/App.less`, then import less file instead.

```
/* src/App.js */
- import './App.css';
+ import './App.less';
```

```
/* src/App.less */
- @import '~antd/dist/antd.css';
+ @import '~antd/dist/antd.less';
```

Then install `craco-less` and modify `craco.config.js` like below.

```
$ yarn add craco-less
```

```
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

### eject[#](https://ant.design/docs/react/use-with-create-react-app#eject) <a href="eject" id="eject"></a>

You can also eject your application using [yarn run eject](https://facebook.github.io/create-react-app/docs/available-scripts#npm-run-eject) for a custom setup of create-react-app, although you should dig into it by yourself.

### Summary[#](https://ant.design/docs/react/use-with-create-react-app#Summary) <a href="summary" id="summary"></a>

Finally, we used antd with create-react-app successfully, the source code of this guide was pushed to [create-react-app-antd](https://github.com/ant-design/create-react-app-antd) which you could clone and use it directly.

Next part, We will introduce how to use antd in [TypeScript](https://ant.design/docs/react/use-in-typescript) and [Umi](https://ant.design/docs/react/practical-projects), let's keep moving!

* [\
  ](https://github.com/afc163)





## Customize Theme

* [Ant Design Less variables](https://ant.design/docs/react/customize-theme#Ant-Design-Less-variables)
* [How to do it](https://ant.design/docs/react/customize-theme#How-to-do-it)
* [How to avoid modifying global styles?](https://ant.design/docs/react/customize-theme#How-to-avoid-modifying-global-styles?)
* [Not working?](https://ant.design/docs/react/customize-theme#Not-working?)
* [Official Themes 🌈](https://ant.design/docs/react/customize-theme#Official-Themes-%F0%9F%8C%88)
* [Related Articles](https://ant.design/docs/react/customize-theme#Related-Articles)

Ant Design allows you to customize our design tokens to satisfy UI diversity from business or brand requirements, including primary color, border radius, border color, etc.

![customized themes](https://zos.alipayobjects.com/rmsportal/zTFoszBtDODhXfLAazfSpYbSLSEeytoG.png)

### Ant Design Less variables[#](https://ant.design/docs/react/customize-theme#Ant-Design-Less-variables) <a href="ant-design-less-variables" id="ant-design-less-variables"></a>

We are using [Less](http://lesscss.org) as the development language for styling. A set of less variables are defined for each design aspect that can be customized to your needs.

There are some major variables below, all less variables could be found in [Default Variables](https://github.com/ant-design/ant-design/blob/master/components/style/themes/default.less).

```
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

### How to do it[#](https://ant.design/docs/react/customize-theme#How-to-do-it) <a href="how-to-do-it" id="how-to-do-it"></a>

We will use [modifyVars](http://lesscss.org/usage/#using-less-in-the-browser-modify-variables) provided by less.js to override the default values of the variables, You can use this [example](https://github.com/ant-design/create-react-app-antd) as a live playground. We now introduce some popular way to do it depends on different workflow.

#### Customize in webpack[#](https://ant.design/docs/react/customize-theme#Customize-in-webpack) <a href="customize-in-webpack" id="customize-in-webpack"></a>

We take a typical `webpack.config.js` file as example to customize its [less-loader](https://github.com/webpack-contrib/less-loader) options.

```
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

#### Customize in Umi[#](https://ant.design/docs/react/customize-theme#Customize-in-Umi) <a href="customize-in-umi" id="customize-in-umi"></a>

You can easily use [theme](https://umijs.org/config/#theme) field in `.umirc.ts` or [config/config.ts](https://github.com/ant-design/ant-design-pro/blob/v5/config/config.ts) file of your project root directory if you are using [Umi](http://umijs.org), which could be an object or a javascript file path.

```
"theme": {
  "primary-color": "#1DA57A",
},
```

Or just [a javascript file path](https://github.com/ant-design/ant-design-pro/blob/b7e7983661eb5e53dc807452e9653e93e74276d4/.webpackrc.js#L18):

```
"theme": "./theme.js",
```

#### Customize in create-react-app[#](https://ant.design/docs/react/customize-theme#Customize-in-create-react-app) <a href="customize-in-create-react-app" id="customize-in-create-react-app"></a>

Follow [Use in create-react-app](https://ant.design/docs/react/use-with-create-react-app).

#### Customize in less file[#](https://ant.design/docs/react/customize-theme#Customize-in-less-file) <a href="customize-in-less-file" id="customize-in-less-file"></a>

Another approach to customize theme is creating a `less` file within variables to override `antd.less`.

```
@import '~antd/lib/style/themes/default.less';
@import '~antd/dist/antd.less'; // Import Ant Design styles by less entry
@import 'your-theme-file.less'; // variables to override above
```

Note: This way will load the styles of all components, regardless of your demand, which cause `style` option of `babel-plugin-import` not working.

#### Dynamic theme[#](https://ant.design/docs/react/customize-theme#Dynamic-theme) <a href="dynamic-theme" id="dynamic-theme"></a>

Runtime update theme color please [ref this doc](https://ant.design/docs/react/customize-theme-variable).

### How to avoid modifying global styles?[#](https://ant.design/docs/react/customize-theme#How-to-avoid-modifying-global-styles) <a href="how-to-avoid-modifying-global-styles" id="how-to-avoid-modifying-global-styles"></a>

Currently ant-design is designed as a whole experience and modify global styles (eg `body` etc). If you need to integrate ant-design as a part of an existing website, it's likely you want to prevent ant-design to override global styles.

While there's no canonical way to do it, you can take one of the following paths :

#### Configure webpack to load an alternate less file and scope global styles[#](https://ant.design/docs/react/customize-theme#Configure-webpack-to-load-an-alternate-less-file-and-scope-global-styles) <a href="configure-webpack-to-load-an-alternate-less-file-and-scope-global-styles" id="configure-webpack-to-load-an-alternate-less-file-and-scope-global-styles"></a>

It's possible to configure webpack to load an alternate less file:

```
new webpack.NormalModuleReplacementPlugin( /node_modules\/antd\/lib\/style\/index\.less/, path.resolve(rootDir, 'src/myStylesReplacement.less') )

#antd { @import '~antd/lib/style/core/index.less'; @import '~antd/lib/style/themes/default.less'; }
```

Where the src/myStylesReplacement.less file loads the same files as the index.less file, but loads them within the scope of a top-level selector : the result is that all of the "global" styles are being applied with the #antd scope.

#### Use a postcss processor to scope all styles[#](https://ant.design/docs/react/customize-theme#Use-a-postcss-processor-to-scope-all-styles) <a href="use-a-postcss-processor-to-scope-all-styles" id="use-a-postcss-processor-to-scope-all-styles"></a>

See an example of usage with [gulp and postcss-prefixwrap](https://gist.github.com/sbusch/a90eafaf5a5b61c6d6172da6ff76ddaa).

### Not working?[#](https://ant.design/docs/react/customize-theme#Not-working) <a href="not-working" id="not-working"></a>

You must import styles as less format. A common mistake would be importing multiple copied of styles that some of them are css format to override the less styles.

* If you import styles by specifying the `style` option of [babel-plugin-import](https://github.com/ant-design/babel-plugin-import), change it from `'css'` to `true`, which will import the `less` version of antd.
* If you import styles from `'antd/dist/antd.css'`, change it to `antd/dist/antd.less`.

### Official Themes 🌈[#](https://ant.design/docs/react/customize-theme#Official-Themes-%F0%9F%8C%88) <a href="official-themes" id="official-themes"></a>

We have some official themes, try them out and give us some feedback!

* 🌑 Dark Theme (supported in 4.0.0+)
* 📦 Compact Theme (supported in 4.1.0+)
* ☁️ [Aliyun Console Theme (Beta)](https://github.com/ant-design/ant-design-aliyun-theme)

#### Use dark or compact theme[#](https://ant.design/docs/react/customize-theme#Use-dark-or-compact-theme) <a href="use-dark-or-compact-theme" id="use-dark-or-compact-theme"></a>

![](https://gw.alipayobjects.com/mdn/rms\_08e378/afts/img/A\*mYU9R4YFxscAAAAAAAAAAABkARQnAQ)

Method 1: using Umi 3

If you're using [Umi 3](http://umijs.org):

```
// .umirc.ts or config/config.ts
export default {
  antd: {
    dark: true, // active dark theme
    compact: true, // active compact theme
  },
},
```

Method 2: Import [antd/dist/antd.dark.less](https://unpkg.com/browse/antd@4.x/dist/antd.dark.less) or [antd/dist/antd.compact.less](https://unpkg.com/browse/antd@4.x/dist/antd.compact.less) in the style file:

```
@import '~antd/dist/antd.dark.less'; // Introduce the official dark less style entry file
@import '~antd/dist/antd.compact.less'; // Introduce the official compact less style entry file
```

If the project does not use Less, you can import [antd.dark.css](https://unpkg.com/browse/antd@4.x/dist/antd.dark.css) or [antd/dist/antd.compact.css](https://unpkg.com/browse/antd@4.x/dist/antd.compact.css) in the CSS file:

```
@import '~antd/dist/antd.dark.css';
@import '~antd/dist/antd.compact.css';
```

> Note that you don't need to import `antd/dist/antd.less` or `antd/dist/antd.css` anymore, please remove it, and remove babel-plugin-import `style` config too. You can't enable two or more theme at the same time by this method.

Method 3: using [less-loader](https://github.com/webpack-contrib/less-loader) in `webpack.config.js` to introduce as needed:

```
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

### Related Articles[#](https://ant.design/docs/react/customize-theme#Related-Articles) <a href="related-articles" id="related-articles"></a>

* [Using Ant Design in Sass-Styled Webpack Projects with `antd-scss-theme-plugin`](https://intoli.com/blog/antd-scss-theme-plugin/)
* [How to Customize Ant Design with React & Webpack… the Missing Guide](https://medium.com/@GeoffMiller/how-to-customize-ant-design-with-react-webpack-the-missing-guide-c6430f2db10f)
* [Theming Ant Design with Sass and Webpack](https://gist.github.com/Kruemelkatze/057f01b8e15216ae707dc7e6c9061ef7)
* [Using Sass/Scss with React App (create-react-app)](https://medium.com/@mzohaib.qc/using-sass-scss-with-react-app-create-react-app-d03072083ef8)
* [Dynamic Theming in Browser using Ant Design](https://medium.com/@mzohaib.qc/ant-design-dynamic-runtime-theme-1f9a1a030ba0)
* [Zero config custom theme generator](https://www.npmjs.com/package/@emeks/antd-custom-theme-generator)
* [\
  ](https://github.com/afc163)





## Replace Moment.js

* [Custom component](https://ant.design/docs/react/replace-moment#Custom-component)
* [antd-dayjs-webpack-plugin](https://ant.design/docs/react/replace-moment#antd-dayjs-webpack-plugin)
* [Use date-fns](https://ant.design/docs/react/replace-moment#Use-date-fns)

You might want to replace Moment.js with another date library (**Ant design currently supports **[**dayjs**](https://day.js.org)** and **[**date-fns**](https://date-fns.org)) to reduce bundle size. We provide two ways to customize:

### Custom component[#](https://ant.design/docs/react/replace-moment#Custom-component) <a href="custom-component" id="custom-component"></a>

The first way is to use `generatePicker` (or `generateCalendar`) to help create Picker components.

First, we initialize an antd demo with `create-react-app`. You can refer to [Use in TypeScript](https://ant.design/docs/react/use-in-typescript), or you can start directly here [init antd](https://github.com/xiaohuoni/antd4-generate-picker/commit/47fec964e36d48bd15760f8f5abcb9655c259aa6)

#### DatePicker.tsx[#](https://ant.design/docs/react/replace-moment#DatePicker.tsx) <a href="datepicker.tsx" id="datepicker.tsx"></a>

Create `src/components/DatePicker.tsx`.

For example:

```
import { Dayjs } from 'dayjs';
import dayjsGenerateConfig from 'rc-picker/lib/generate/dayjs';
import generatePicker from 'antd/es/date-picker/generatePicker';
import 'antd/es/date-picker/style/index';

const DatePicker = generatePicker<Dayjs>(dayjsGenerateConfig);

export default DatePicker;
```

#### TimePicker.tsx[#](https://ant.design/docs/react/replace-moment#TimePicker.tsx) <a href="timepicker.tsx" id="timepicker.tsx"></a>

Create `src/components/TimePicker.tsx`.

For example:

```
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

#### Calendar.tsx[#](https://ant.design/docs/react/replace-moment#Calendar.tsx) <a href="calendar.tsx" id="calendar.tsx"></a>

Create `src/components/Calendar.tsx`.

For example:

```
import { Dayjs } from 'dayjs';
import dayjsGenerateConfig from 'rc-picker/lib/generate/dayjs';
import generateCalendar from 'antd/es/calendar/generateCalendar';
import 'antd/es/calendar/style';

const Calendar = generateCalendar<Dayjs>(dayjsGenerateConfig);

export default Calendar;
```

#### Export Custom component[#](https://ant.design/docs/react/replace-moment#Export-Custom-component) <a href="export-custom-component" id="export-custom-component"></a>

Create `src/components/index.tsx`.

For example:

```
export { default as DatePicker } from './DatePicker';
export { default as Calendar } from './Calendar';
export { default as TimePicker } from './TimePicker';
```

#### Use Custom component[#](https://ant.design/docs/react/replace-moment#Use-Custom-component) <a href="use-custom-component" id="use-custom-component"></a>

Modify `src/App.tsx`,import `dayjs` and custom component.

```
- import { DatePicker, Calendar } from 'antd';
- import format from 'moment';

+ import { DatePicker, TimePicker, Calendar } from './components';
+ import format from 'dayjs';
```

If the above steps do not work correctly, you can refer to [antd4-generate-picker/antd-ts](https://github.com/xiaohuoni/antd4-generate-picker/tree/master/antd-ts).

If you need JavaScript code, you can refer to [antd4-generate-picker/antd-demo](https://github.com/xiaohuoni/antd4-generate-picker/tree/master/antd-demo).

If you use [umi](https://umijs.org), you can reference [antd4-use-dayjs-replace-moment](https://github.com/xiaohuoni/antd4-use-dayjs-replace-moment).

### antd-dayjs-webpack-plugin[#](https://ant.design/docs/react/replace-moment#antd-dayjs-webpack-plugin) <a href="antd-dayjs-webpack-plugin" id="antd-dayjs-webpack-plugin"></a>

We also provide another implementation, which we provide with `antd-dayjs-webpack-plugin`, replacing `momentjs` with `Day.js` directly without changing a line of existing code. More info can be found at [antd-dayjs-webpack-plugin](https://github.com/ant-design/antd-dayjs-webpack-plugin).

```
// webpack-config.js
import AntdDayjsWebpackPlugin from 'antd-dayjs-webpack-plugin';

module.exports = {
  // ...
  plugins: [new AntdDayjsWebpackPlugin()],
};
```

### Use date-fns[#](https://ant.design/docs/react/replace-moment#Use-date-fns) <a href="use-date-fns" id="use-date-fns"></a>

[date-fns](https://date-fns.org) currently supports custom component methods similar to `dayjs`. The difference is that the parameter types used are different. Support is provided in antd 4.5.0 and above.

For Example:

#### DatePicker.tsx[#](https://ant.design/docs/react/replace-moment#DatePicker.tsx) <a href="datepicker.tsx" id="datepicker.tsx"></a>

Create `src/components/DatePicker.tsx`.

Code as follows:

```
import dateFnsGenerateConfig from 'rc-picker/lib/generate/dateFns';
import generatePicker from 'antd/es/date-picker/generatePicker';
import 'antd/es/date-picker/style/index';

const DatePicker = generatePicker<Date>(dateFnsGenerateConfig);

export default DatePicker;
```

[\
](https://github.com/afc163)

## FAQ:

## Design Critiques

### What are Design Critiques?

In Design Critiques, UX Engineers meet with the Design Manager at least once per sprint to present their design progress and planning for group discussion.

### Our Goals

**Go Deeper on Core Design Concepts**

These sessions are an opportunity to empower you with a more nuanced understanding of UI/UX that you can **carry into interviews**.

**Reinforce the Curriculum**

By walking through active projects together throughout development, we'll naturally encounter **clear, real-world case studies** that provide examples of best practices.

**Level Up Your Product's Quality**

Design Critiques are a great opportunity to practice **giving and receiving feedback** in the context of team development.

### Agenda

#### Pick Volunteers

We'll pick on a few UX Engineers to walk us through what they're working on!

#### Design Lead Presentations

**Introduction**

Each UX Engineer on the presenting team should give a _very brief_ introduction of themselves and their design experience, then they should introduce their product to provide context.

**Product Demo**

With someone sharing their screen, the UX Engineer should collaboratively walk through either the live deployed version or a relevant local version of the product. The Design Manager facilitates a group discussion identifying aspects of the product demonstrating good UI/UX principles as well as aspects needing improvement.

**Planning Artifact Presentation**

With someone sharing their screen, the Design Leads should collaboratively walk through any design planning artifacts they've got (e.g. user flows, wireframes). The Design Manager facilitates a group discussion about the artifacts, the general design direction, and UI/UX concerns relevant to their product.

Now read on to see how **Product Reviews** work in Labs.



