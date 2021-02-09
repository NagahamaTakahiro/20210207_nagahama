<template>
  <div class="header">
    <input type="text" maxlength="7" v-model="childText" />
    <button @click="sendParent">住所自動入力</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  methods: {
    sendParent() {
      const data = await axios.get(
      `https://apis.postcode-jp.com/api/v3/postcodes/postcode?apiKey=PQF7Paak29Wr688IIVCXC7As7YDPMBGko0KBwdF&postcode={{childText}}`
      ),
      props: ["parentText"]
    };
  };
};
</script>