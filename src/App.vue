<template>
  <div class="header">
    <input type="text" maxlength="7" v-model="childText" />
    <button @click="sendParent">住所自動入力</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      childText: "",
      // データ内で定義する必要があります
      Address ：　["addressData"];
    }
  },
  methods: {
    async sendParent() {
      const data = await axios.get(
      `https://apis.postcode-jp.com/api/v3/postcodes/${this.childText}apiKey=PQF7Paak29Wr688IIVCXC7As7YDPMBGko0KBwdF`);
      //  data.data[0].allAddress;これで住所のデータを取得できます！
    }
    const data = "addressData";
  }
};
</script>