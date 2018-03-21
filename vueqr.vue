<template>
  <div ref="qr" class="qrBox">
    <img :src="src">
  </div>
</template>

<script>
import QRCode from 'qrcode'
export default {
  data() {
    return {
      src: '',
      textBase: 'demo',
      configBase: {
        // 容错等级
        errorCorrectionLevel: 'H',
        // 图片类型
        type: 'image/png',
        rendererOpts: {
          quality: 0.3
        },
        // 边框与二维码之间的间距
        margin: 2,
        // 缩放倍数
        scale: 4,
        width: 500,
        maskPattern: 1,
        color: {
          dark: '#000000',
          light: '#ffffff'
        },
        style: {
          width: '128px',
          border: '1px solid #ccc'
        }
      }
    }
  },
  props: ['config', 'text'],
  mounted() {
    this.makeQRCode(this.config, this.text)
  },
  methods: {
    makeQRCode(config, text) {
      QRCode.toDataURL(
        text || this.textBase,
        config || this.configBase,
        (err, url) => {
          console.log(err)
          this.src = url
        })
      if (!config) {
        for (const k in this.configBase.style) {
          this.$refs.qr.style[k] = this.configBase.style[k]
        }
      } else {
        for (const k in config.style) {
          this.$refs.qr.style[k] = this.config.style[k]
        }
      }
    }
  }
}
</script>
<style>
.qrBox img {
  vertical-align: top;
  width: 100%;
  height: 100%;
}
</style>
