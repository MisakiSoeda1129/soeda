<template>
  <div id="app" class="accordion">
    <div type=" button" :class="isOpen" @click="accordionToggle()" class="ttl-accordion">
      <p class="ttl-accordion__item">アコーディオン</p>
    </div>
    <div :class="isOpen" v-if="isOpen" class="content-accordion">
        <p class="content-accordion__item">アコーディオンの中身が入ります</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      //初期値消す
      isOpen: false
    };
  },
  methods: {
    accordionToggle: function() {
      //isOpenとは逆(true)を代入？ ここよく理解してません。
      this.isOpen = !this.isOpen;
    },
  }
};
</script>

<style scoped>
.accordion {
  border: 1px solid #000;
}
.ttl-accordion {
  background-color: #ccc;
  cursor: pointer;
}
.ttl-accordion__item {
  padding: 20px 15px;
  margin: 0;
}
.content-accordion {}
.content-accordion__item {
  padding: 10px 25px;
  font-size: 0.8rem;
}
</style>