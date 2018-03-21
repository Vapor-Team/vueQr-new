# vue components

  [![npm](https://img.shields.io/npm/v/vueqr-new.svg?style=flat-square)](https://www.npmjs.com/package/vueqr-new)
  [![npm](https://img.shields.io/npm/dt/vueqr-new.svg?style=flat-square)](https://www.npmjs.com/package/vueqr-new)
  [![npm](https://img.shields.io/npm/l/vueqr-new.svg?style=flat-square)](https://github.com/Jack-In/vueQr-new/master/license)

> ### 快速安装
  ### install
  快速添加 `vueqr-new` 组件到 app 中
  ```bash
  npm install --save vueqr-new
  ```
  ### components
  ```html
  <template>
    <div>
      <vue-qr :config="config" :text="text"></vue-qr>
    </div>
  </template>
  // 入口文件
    使用Vue.use()来注册该组件库
    import JackUI from 'vueqr-new'
    Vue.use(JackUI)
  <script>
  const config = {
    // 容错等级
    errorCorrectionLevel: 'H',
    // 图片类型
    type: 'image/png',
    rendererOpts: {
    quality: 0.3
    },
    // 边框与二维码之间的间距
    margin: 0,
    // 缩放倍数
    scale: 4,
    width: 500,
    maskPattern:1,
    color: {
    dark: '#000000',
    light : "#ffffff"
    },
    style: {
    width: '128px',
    border: '1px solid #ccc'
    }
  }
  export default {
    data() {
      return {
        text: 'https://example.com',
        config: config
      }
    }
  }
  </script>
  ```
## Component props

| 属性 | 类型 | 属性描述 |
|------|------|--------------|---------|
| config | Object | qrcode option |
| text | String | qrcode value |

## 参考代码
["node-qrcode"](https://github.com/zpao/qrcode.react)
> ### License

[MIT](https://github.com/Jack-In/vueQr-new/blob/master/LICENSE)
