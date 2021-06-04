<template>
  <div id="app">
    <div id="nav">
      <!-- これは表示させるためのvue -->
      <input type="text" maxlength="7" v-model="addressNum">
      <button @click="getAddress">住所自動入力</button>
      <!-- v-modelで表示 -->
      <p>Address：{{ address }}</p>
    </div>
  </div>
</template>

<script>
//APIを使用するためaxiosをimportする
import axios from "axios";

export default {
  data() {
    return {
      addressNum: "",
      address: ""
    };
  },
  methods: {
    async getAddress() {
      //axios仕様でAPIを叩く
      const item = await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.addressNum}?apiKey=Z3ojzPfVaULjFnWNcXhQeOaqGH08YNGefTwT2Kc`);

      //APIからの情報を受け止める
      const addressData = item.data[0];

      //何も情報がない時にエラーが出るのでif文で対策
      if(addressData) {
        this.address = addressData.allAddress;
      }
    }
  }
};
</script>
