---
order: 10
title:
  zh-CN: 按钮组合
  en-US: Rtl Button
---

## zh-CN

可以将多个 `Rtl Button` 放入 `Button.Group` 的容器中。

通过设置 `size` 为 `large` `small` 分别把按钮组合设为大、小尺寸。若不设置 `size`，则尺寸为中。

## en-US

button component supports rtl direction if placed inside `ConfigProvider` with `layoutDirection='rtl'`

```jsx
import { ConfigProvider, Button, Icon } from 'antd';

const ButtonGroup = Button.Group;

class App extends React.Component {
  state = {
    loading: false,
    iconLoading: false,
  };

  enterLoading = () => {
    this.setState({ loading: true });
  };

  enterIconLoading = () => {
    this.setState({ iconLoading: true });
  };

  render() {
    return (
      <div>
        <ConfigProvider layoutDirection="rtl">
          <h4>Right To Left</h4>
          <ButtonGroup>
            <Button>لغو</Button>
            <Button>تایید</Button>
          </ButtonGroup>
          <ButtonGroup>
            <Button disabled>L</Button>
            <Button disabled>M</Button>
            <Button disabled>R</Button>
          </ButtonGroup>
          <ButtonGroup>
            <Button>L</Button>
            <Button>M</Button>
            <Button>R</Button>
          </ButtonGroup>

          <h4>With Icon</h4>
          <ButtonGroup>
            <Button type="primary">
              <Icon type="right" />
              قبلی
            </Button>
            <Button type="primary">
              بعدی
              <Icon type="left" />
            </Button>
          </ButtonGroup>
          <ButtonGroup>
            <Button type="primary" icon="cloud" />
            <Button type="primary" icon="cloud-download" />
          </ButtonGroup>
          <h4>Loading</h4>
          <Button type="primary" loading>
            بارگذاری
          </Button>
          <Button type="primary" size="small" loading>
            بارگذاری
          </Button>
          <br />
          <Button type="primary" loading={this.state.loading} onClick={this.enterLoading}>
            کلیک کنید !
          </Button>
          <Button
            type="primary"
            icon="poweroff"
            loading={this.state.iconLoading}
            onClick={this.enterIconLoading}
          >
            کلیک کنید !
          </Button>
          <br />
          <Button shape="circle" loading />
          <Button type="primary" shape="circle" loading />
        </ConfigProvider>
      </div>
    );
  }
}
ReactDOM.render(<App />, mountNode);
```

<style>
#components-button-demo-right-to-left h4 {
  margin: 16px 0;
  font-size: 14px;
  line-height: 1;
  font-weight: normal;
}
#components-button-demo-right-to-left h4:first-child {
  margin-top: 0;
}
#components-button-demo-right-to-left .ant-btn-group {
  margin-left: 8px;
}
</style>
