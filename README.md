# vue components

  [![npm](https://img.shields.io/npm/v/vueqr-new.svg?style=flat-square)](https://www.npmjs.com/package/vueqr-new)
  [![npm](https://img.shields.io/npm/dt/vueqr-new.svg?style=flat-square)](https://www.npmjs.com/package/vueqr-new)
  [![npm](https://img.shields.io/npm/l/vueqr-new.svg?style=flat-square)](https://github.com/Jack-In/vueQr-new/master/license)

> ### Usage
  ### install
  ```shell
  npm install --save qrcode vueqr-new
  ```
  ### components
  ```html
  <vue-qr :config="config" :text="demo"></vue-qr>
  ```
  ### option
  ```javascript3
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
  ```
> ### License

[MIT](https://github.com/Jack-In/vueQr-new/blob/master/LICENSE)
