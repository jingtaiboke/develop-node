```
<!--
  size
    mini
    default

  type 控制颜色
    primary
    warn

  plain 镂空

  loading 名称前是否带loading图标
-->
<button size="mini" type="primary" plain>默认按钮</button>
<button size="mini" type="primary" loading>默认按钮</button>

<!--
  button开放能力
  open-type:
  1 contact 直接打开 客服对话功能 需要在微信小程序的后台配置
  2 share 转发当前的小程序 到微信朋友圈中 不能分享到朋友圈
  3 getPhoneNumber 获取当前用户手机号码信息 结合一个事件使用 不是企业账号 没有权限获取
    3.1 绑定一个事件 bindgetphonenUmber
    3.2 在事件回调中 通过参数来获取信息
    3.3 获取到的信息已加密过
  4 getUserINfo 获取当前用的个人信息
    通过绑定事件  bindgetuserinfo 获取用户信息
  5 launchApp 在小程序当中 直接打开App
    5.1 需要先在 app中 通过app的某个链接 打开小程序
    5.2 在小程序中 通过 这个 功能 重新打开 app
  6 openSetting 打开小程序中内置的授权界面
    6.1 授权页面中 只会出现 用户曾经点击过的 权限
  7 feedback 打开小程序内置的 意见反馈界面
    7.1只能过真机调试
-->
<button open-type="contact">contact</button>
<button open-type="share">share</button>
<button open-type="getPhoneNumber" bindgetphonenUmber="getPhoneNumber">getPhoneNumber</button>
<button open-type="getUserInfo" bindgetuserinfo="getUserInfo">getUserInfo</button>
<button open-type="launchApp">launchApp</button>
<button open-type="openSetting">openSetting</button>
<button open-type="feedback">feedback</button>

<!--
  小程序中的字体图标
  size大小(默认23)
  color颜色
-->
<icon type="success" color="blue" size="50"></icon>
```

