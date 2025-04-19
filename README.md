# Donate-page

> 💸 我很可爱，请给我钱 ww

一键打钱（大误）提供从浏览器跳转至支付宝/微信支付/QQ 支付/Paypal 的能力，帮助个人开发者完成打赏功能实现。

> 示例页面： **[快来打钱快来打钱～疯狂暗示 wink 😘](https://donate.techisle.top)**

- PC 端显示效果

<a href="https://donate.techisle.top" target="_blank"><img src="https://i.loli.net/2021/09/24/bDRBvuknsKTpafW.png" alt="PC"></a>

- 移动端显示效果

<a href="https://donate.techisle.top" target="_blank"><img src="https://i.loli.net/2021/09/24/L8vdo1c9uRfmAq6.png" width="250" alt="Mobile"></a>

本项目基于 [hifocus/merger](https://github.com/hifocus/merger) 上开发 ~~但其实基本把大部分代码都重新写了个遍~~ 在项目基础上实现的 Feature：

- JSON 文件轻松配置 三分钟搭建自己的捐赠页
- 所有文案表述全部走配置，在 JSON 中自定义全部文案
- 🌟 适配移动端，支持最完善的直接调起功能
  - 网页加载完成时/选择支付宝时，支持直接调起支付宝
  - 微信内打开时，长按图片即可直接调起微信付款码
  - 针对 iOS 手机，保存微信/QQ 二维码后，支持直接调起微信/手机 QQ 扫码页
  - 在 Android/iOS 多款手机、浏览器进行过兼容性测试，确保图片可被保存
- 小改了一下页面的样式，能更显著显示投喂按钮
- 大改了实现逻辑，生成页面更静态，性能更好

![](https://i.loli.net/2021/09/26/LenDzqSHZsMgNrF.png)

## 快速开始

提前安装 [yarn](https://yarnpkg.com/)

```sh
# 安装依赖
yarn

# 开发
yarn dev

# 构建
yarn build
```

之后在 `dist` 目录即为成品

## 页面信息配置

修改 config.json 即可配置页面信息，修改后重新执行 yarn dev 即可看到效果。

当然，您也可以对页面 HTML 进行拓展，页面使用 [EJS 模版](https://ejs.bootcss.com/)。

```javascript
{
  "profile": "statics/my-avatar.png",
  "name": "cubeyu",
  "description": "来给麦希屿投喂棒棒糖吧🍭",
  "qrlogo": "statics/icon.png",
  "alipay": {
    "title": "😘支付宝扫一扫 投喂麦希屿",
    "othertitle": "长按图片保存，在支付宝打开<br />😘感谢投喂",
    "url": "https://qr.alipay.com/a6x11732pyuue0s59mdzp97",
    "open_url": "alipays://platformapi/startapp?appId=10000007&qrcode=https://qr.alipay.com/a6x11732pyuue0s59mdzp97",
    "savetext": "保存二维码"
  },
  "wechatpay": {
    "title": "😘微信扫一扫 投喂麦希屿",
    "othertitle": "长按图片保存，在微信打开<br />😘感谢投喂",
    "url": "wxp://f2f04oJmM0v3ZQRHp_ci_LWhGAE1MGmnug9q70bIAGQmdeo",
    "savetext": "保存二维码",
    "wechattitle": "😘长按图片扫一扫 投喂麦希屿",
    "wechattext": "如使用其他方式付款，请点击右上角<br />并选择”在浏览器打开“",
    "toapptext": "保存完成，去微信扫一扫"
  },
  "tenpay": {
    "title": "😘手机QQ扫一扫 投喂麦希屿",
    "othertitle": "长按图片保存，在手机QQ打开<br />😘感谢投喂",
    "url": "https://i.qianbao.qq.com/wallet/sqrcode.htm?m=tenpay&f=wallet&a=1&u=3144855127&n=%E9%BA%A6%E5%B8%8C%E5%B1%BF&ac=CAEQ19zK2wsY0YOPwAYyGOiBiuWkqeWcuuaZr-e7j-iQpeaUtuasvjgBQiA0NmQ4NjI4OTZjNmFkY2RhYzlmZjZlZTBhYTRkNWU4NQ%3D%3D_xxx_sign",
    "savetext": "保存二维码",
    "toapptext": "保存完成，去手机QQ扫一扫"
  },
  "paypal": {
    "url": "https://paypal.me/maixiyu?country.x=C2&locale.x=zh_XC"
  }
}
```

## Open Source License

This project is under [GNU General Public License v3.0](./LICENSE).

Based on following open source projects:

- [hifocus/merger](https://github.com/hifocus/merger)
- [Automattic/node-canvas](https://github.com/Automattic/node-canvas)
- [soldair/node-qrcode](https://github.com/soldair/node-qrcode)
- [faisalman/ua-parser-js](https://github.com/faisalman/ua-parser-js)
