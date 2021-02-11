<template>
  <div class="header">
    <input type="text" maxlength="7" v-model="childText" />
    <button @click="sendParent">住所自動入力</button>
    <p>Address：{{addressData}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      addressData:"",
      childText:""
    }
  },
  methods: {
    async sendParent() {
      const data = await axios.get(
      `https://apis.postcode-jp.com/api/v3/postcodes/${this.childText}?apiKey=PQF7Paak29Wr688IIVCXC7As7YDPMBGko0KBwdF`);
      //  data.data[0].allAddress;これで住所のデータを取得できます！
      console.log(data)
      this.addressData = data.data[0].allAddress;
    }
  }
  date.get();
};
</script>