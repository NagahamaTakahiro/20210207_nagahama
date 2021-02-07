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
      childText: ""
    },
    async created() {
    const data = await axios.get(
      `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=PQF7Paak29Wr688IIVCXC7As7YDPMBGko0KBwdF`
    );
  },
  methods: {
    sendParent() {
      this.$emit("getChildText", this.childText);
    }
  }
};
</script>