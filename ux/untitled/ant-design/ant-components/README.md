# ANT Components



## Forms <a id="forms"></a>

#### Example Form <a id="example-form"></a>

* Here's an example of building a basic form using our reusable `FormInput` & `FormButton` components. You can use these to build out different types of forms throughout your application:

```text
import { FormInput, FormButton } from './components/common';<form onSubmit={handleSubmit}>  <FormInput placeholder="Email" name="email" labelId="User Email" />  <FormButton buttonText="Submit" classType="default" disabled="false" /></form>Copy
```

* Note that we are importing our components from `./components/common`. This is the directory where any of your custom reusable components should live.

#### Ant Design Form <a id="ant-design-form"></a>

* Here's is an example of creating a basic form using Ant Design components:

```text
import { Form, Input, Button } from 'antd';<Form onFinish={handleSubmit}>  <Form.Item    label="My Input"  >    <Input />  </Form.Item>  <Form.Item>    <Button type="primary" htmlType="submit">      Submit    </Button>  </Form.Item></Form>Copy
```

* Note that each child component of the form needs to be wrapped in a `Form.Item` component for Ant Design's layout to work.
* To customize the layout of our form we can create a `layout` object and make use of [Ant Design's grid system](https://ant.design/components/grid/):

```text
const layout = {   // This specifies how wide we want our form container (wrapper) to be,   // where a span of 24 is equivalent to 100%.    wrapperCol: {      span: 8,    }  };  // To use our layout we can spread our layout object on our Form component:  <Form onFinish={handleSubmit} {...layout}>  <Form.Item    label="My Input"  >    <Input />  </Form.Item>  <Form.Item>    <Button type="primary" htmlType="submit">      Submit    </Button>  </Form.Item></Form>Copy
```

* You can also specify the grid layouts for each `Form.Item` component:

```text
const itemLayout = {  wrapperCol: { offset: 4, span: 8 },}<Form onFinish={handleSubmit} {...layout}>  <Form.Item    label="My Input"  >    <Input />  </Form.Item>  <Form.Item {...itemLayout}>    <Button type="primary" htmlType="submit">      Submit    </Button>  </Form.Item></Form>Copy
```

* Adding form validation with Ant Design is really simple! We can specify a rules array with an error type and the message we would like to display on that error:

```text
const myRules = [  {    required: true,    message: 'Please input your email!',  },  {    type: 'email',    message: 'Please enter a valid email',  },];<Form onFinish={handleSubmit} {...layout}>  <Form.Item    label="Email"    name="email"    rules={myRules}  >    <Input />  </Form.Item>  <Form.Item {...itemLayout}>    <Button type="primary" htmlType="submit">      Submit    </Button>  </Form.Item></Form>Copy
```

* Note that we have to add a `name` prop to our input in order for our validation rules to take effect.
* For more detail on using the Ant Design `Form` component check out the [Ant Design Docs](https://ant.design/components/form/).









## Components Overview

`antd` provides plenty of UI components to enrich your web applications, and we will improve components experience consistently. We also recommend some great [Third-Party Libraries](https://ant.design/docs/react/recommendation) additionally.

### General3

[Button![Button](https://gw.alipayobjects.com/zos/alicdn/fNUKzY1sk/Button.svg)](https://ant.design/components/button/)[Icon![Icon](https://gw.alipayobjects.com/zos/alicdn/rrwbSt3FQ/Icon.svg)](https://ant.design/components/icon/)[Typography![Typography](https://gw.alipayobjects.com/zos/alicdn/GOM1KQ24O/Typography.svg)](https://ant.design/components/typography/)

### Layout4

[Divider![Divider](https://gw.alipayobjects.com/zos/alicdn/5swjECahe/Divider.svg)](https://ant.design/components/divider/)[Grid![Grid](https://gw.alipayobjects.com/zos/alicdn/5rWLU27so/Grid.svg)](https://ant.design/components/grid/)[Layout![Layout](https://gw.alipayobjects.com/zos/alicdn/hzEndUVEx/Layout.svg)](https://ant.design/components/layout/)[Space![Space](https://gw.alipayobjects.com/zos/antfincdn/wc6%263gJ0Y8/Space.svg)](https://ant.design/components/space/)

### Navigation7

[Affix![Affix](https://gw.alipayobjects.com/zos/alicdn/tX6-md4H6/Affix.svg)](https://ant.design/components/affix/)[Breadcrumb![Breadcrumb](https://gw.alipayobjects.com/zos/alicdn/9Ltop8JwH/Breadcrumb.svg)](https://ant.design/components/breadcrumb/)[Dropdown![Dropdown](https://gw.alipayobjects.com/zos/alicdn/eedWN59yJ/Dropdown.svg)](https://ant.design/components/dropdown/)[Menu![Menu](https://gw.alipayobjects.com/zos/alicdn/3XZcjGpvK/Menu.svg)](https://ant.design/components/menu/)[Pagination![Pagination](https://gw.alipayobjects.com/zos/alicdn/1vqv2bj68/Pagination.svg)](https://ant.design/components/pagination/)[PageHeader![PageHeader](https://gw.alipayobjects.com/zos/alicdn/6bKE0Cq0R/PageHeader.svg)](https://ant.design/components/page-header/)[Steps![Steps](https://gw.alipayobjects.com/zos/antfincdn/UZYqMizXHaj/Steps.svg)](https://ant.design/components/steps/)

### Data Entry17

[AutoComplete![AutoComplete](https://gw.alipayobjects.com/zos/alicdn/qtJm4yt45/AutoComplete.svg)](https://ant.design/components/auto-complete/)[Checkbox![Checkbox](https://gw.alipayobjects.com/zos/alicdn/8nbVbHEm_/CheckBox.svg)](https://ant.design/components/checkbox/)[Cascader![Cascader](https://gw.alipayobjects.com/zos/alicdn/UdS8y8xyZ/Cascader.svg)](https://ant.design/components/cascader/)[DatePicker![DatePicker](https://gw.alipayobjects.com/zos/alicdn/RT_USzA48/DatePicker.svg)](https://ant.design/components/date-picker/)[Form![Form](https://gw.alipayobjects.com/zos/alicdn/ORmcdeaoO/Form.svg)](https://ant.design/components/form/)[InputNumber![InputNumber](https://gw.alipayobjects.com/zos/alicdn/XOS8qZ0kU/InputNumber.svg)](https://ant.design/components/input-number/)[Input![Input](https://gw.alipayobjects.com/zos/alicdn/xS9YEJhfe/Input.svg)](https://ant.design/components/input/)[Mentions![Mentions](https://gw.alipayobjects.com/zos/alicdn/0pF5j477V/Mentions.svg)](https://ant.design/components/mentions/)[Rate![Rate](https://gw.alipayobjects.com/zos/alicdn/R5uiIWmxe/Rate.svg)](https://ant.design/components/rate/)[Radio![Radio](https://gw.alipayobjects.com/zos/alicdn/8cYb5seNB/Radio.svg)](https://ant.design/components/radio/)[Switch![Switch](https://gw.alipayobjects.com/zos/alicdn/zNdJQMhfm/Switch.svg)](https://ant.design/components/switch/)[Slider![Slider](https://gw.alipayobjects.com/zos/alicdn/HZ3meFc6W/Silder.svg)](https://ant.design/components/slider/)[Select![Select](https://gw.alipayobjects.com/zos/alicdn/_0XzgOis7/Select.svg)](https://ant.design/components/select/)[TreeSelect![TreeSelect](https://gw.alipayobjects.com/zos/alicdn/Ax4DA0njr/TreeSelect.svg)](https://ant.design/components/tree-select/)[Transfer![Transfer](https://gw.alipayobjects.com/zos/alicdn/QAXskNI4G/Transfer.svg)](https://ant.design/components/transfer/)[TimePicker![TimePicker](https://gw.alipayobjects.com/zos/alicdn/h04Zsl98I/TimePicker.svg)](https://ant.design/components/time-picker/)[Upload![Upload](https://gw.alipayobjects.com/zos/alicdn/QaeBt_ZMg/Upload.svg)](https://ant.design/components/upload/)

### Data Display19

[Avatar![Avatar](https://gw.alipayobjects.com/zos/antfincdn/aBcnbw68hP/Avatar.svg)](https://ant.design/components/avatar/)[Badge![Badge](https://gw.alipayobjects.com/zos/antfincdn/6%26GF9WHwvY/Badge.svg)](https://ant.design/components/badge/)[Comment![Comment](https://gw.alipayobjects.com/zos/alicdn/ILhxpGzBO/Comment.svg)](https://ant.design/components/comment/)[Collapse![Collapse](https://gw.alipayobjects.com/zos/alicdn/IxH16B9RD/Collapse.svg)](https://ant.design/components/collapse/)[Carousel![Carousel](https://gw.alipayobjects.com/zos/antfincdn/%24C9tmj978R/Carousel.svg)](https://ant.design/components/carousel/)[Card![Card](https://gw.alipayobjects.com/zos/alicdn/keNB-R8Y9/Card.svg)](https://ant.design/components/card/)[Calendar![Calendar](https://gw.alipayobjects.com/zos/antfincdn/dPQmLq08DI/Calendar.svg)](https://ant.design/components/calendar/)[Descriptions![Descriptions](https://gw.alipayobjects.com/zos/alicdn/MjtG9_FOI/Descriptions.svg)](https://ant.design/components/descriptions/)[Empty![Empty](https://gw.alipayobjects.com/zos/alicdn/MNbKfLBVb/Empty.svg)](https://ant.design/components/empty/)[Image![Image](https://gw.alipayobjects.com/zos/antfincdn/D1dXz9PZqa/image.svg)](https://ant.design/components/image/)[List![List](https://gw.alipayobjects.com/zos/alicdn/5FrZKStG_/List.svg)](https://ant.design/components/list/)[Popover![Popover](https://gw.alipayobjects.com/zos/alicdn/1PNL1p_cO/Popover.svg)](https://ant.design/components/popover/)[Statistic![Statistic](https://gw.alipayobjects.com/zos/antfincdn/rcBNhLBrKbE/Statistic.svg)](https://ant.design/components/statistic/)[Tree![Tree](https://gw.alipayobjects.com/zos/alicdn/Xh-oWqg9k/Tree.svg)](https://ant.design/components/tree/)[Tooltip![Tooltip](https://gw.alipayobjects.com/zos/alicdn/Vyyeu8jq2/Tooltp.svg)](https://ant.design/components/tooltip/)[Timeline![Timeline](https://gw.alipayobjects.com/zos/antfincdn/vJmo00mmgR/Timeline.svg)](https://ant.design/components/timeline/)[Tag![Tag](https://gw.alipayobjects.com/zos/alicdn/cH1BOLfxC/Tag.svg)](https://ant.design/components/tag/)[Tabs![Tabs](https://gw.alipayobjects.com/zos/antfincdn/lkI2hNEDr2V/Tabs.svg)](https://ant.design/components/tabs/)[Table![Table](https://gw.alipayobjects.com/zos/alicdn/f-SbcX2Lx/Table.svg)](https://ant.design/components/table/)

### Feedback10

[Alert![Alert](https://gw.alipayobjects.com/zos/alicdn/8emPa3fjl/Alert.svg)](https://ant.design/components/alert/)[Drawer![Drawer](https://gw.alipayobjects.com/zos/alicdn/7z8NJQhFb/Drawer.svg)](https://ant.design/components/drawer/)[Modal![Modal](https://gw.alipayobjects.com/zos/alicdn/3StSdUlSH/Modal.svg)](https://ant.design/components/modal/)[Message![Message](https://gw.alipayobjects.com/zos/alicdn/hAkKTIW0K/Message.svg)](https://ant.design/components/message/)[Notification![Notification](https://gw.alipayobjects.com/zos/alicdn/Jxm5nw61w/Notification.svg)](https://ant.design/components/notification/)[Progress![Progress](https://gw.alipayobjects.com/zos/alicdn/xqsDu4ZyR/Progress.svg)](https://ant.design/components/progress/)[Popconfirm![Popconfirm](https://gw.alipayobjects.com/zos/alicdn/fjMCD9xRq/Popconfirm.svg)](https://ant.design/components/popconfirm/)[Result![Result](https://gw.alipayobjects.com/zos/alicdn/9nepwjaLa/Result.svg)](https://ant.design/components/result/)[Spin![Spin](https://gw.alipayobjects.com/zos/alicdn/LBcJqCPRv/Spin.svg)](https://ant.design/components/spin/)[Skeleton![Skeleton](https://gw.alipayobjects.com/zos/alicdn/KpcciCJgv/Skeleton.svg)](https://ant.design/components/skeleton/)

### Other3

[Anchor![Anchor](https://gw.alipayobjects.com/zos/alicdn/_1-C1JwsC/Anchor.svg)](https://ant.design/components/anchor/)[BackTop![BackTop](https://gw.alipayobjects.com/zos/alicdn/tJZ5jbTwX/BackTop.svg)](https://ant.design/components/back-top/)[ConfigProvider![ConfigProvider](https://gw.alipayobjects.com/zos/alicdn/kegYxl1wj/ConfigProvider.svg)](https://ant.design/components/config-provider/)





GRID:



