<template>
  <div ref="qr" class="qrBox"></div>
</template>

<script>
import QRCode from './js/qrcode.js'
export default {
  data() {
    return {
      configBase: {
        text: 'test',
        width: 500,
        height: 500,
        colorDark: '#000000',
        colorLight: '#ffffff',
        correctLevel: QRCode.CorrectLevel.H
      }
    }
  },
  props: ['config', 'text'],
  mounted() {
    this.makeQRCode(this.config)
  },
  methods: {
    makeQRCode(config) {
      this.config.text = this.text
      new QRCode(this.$refs.qr, config || this.configBase)
      this.$refs.qr.children[1].width = '128'
      if (!config) {
        for (const k in this.configBase.style) {
          this.$refs.qr.style[k] = this.configBase.style[k]
        }
      } else {
        config.correctLevel = QRCode.CorrectLevel.H
        for (const k in config.style) {
          this.$refs.qr.style[k] = this.config.style[k]
        }
      }
    }
  }
}
</script>
<style>
.qrBox canvas {
  width: 128px;
  height: 128px;
}
</style>

