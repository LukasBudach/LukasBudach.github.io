<template>
  <h1> Home Page </h1>

  <button @click="generateQRCode"> Get QR Code </button>
  <svg ref="qrcode"></svg>
</template>

<script>
import QRCode from "qrcode";

export default {
  name: "HomePage",
  methods: {
    async generateQRCode() {
      this.$refs.qrcode.innerHTML = await QRCode.toString("localhost:8080/about", {
        errorCorrectionLevel: "M",
        width: 150,
        type: "svg",
      });
    }
  }
}
</script>
