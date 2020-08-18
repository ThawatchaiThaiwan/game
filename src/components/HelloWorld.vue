<template>
  <div class="hello">
    <button @click="bottoon" class="bottoom">Start {{randomDamage(1,50)}}</button>
    <button @click="bottoon" class="bottoom">TWO DAMAGE {{randomDamage2(10,100)}}</button>
    <h1>{{ msg }}</h1>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      counter: 0,
      fsize: 50,
    };
  },
  props: {
    lable: String,
  },
  methods: {
    randomDamage: function (min, max) {
    this.randomNo=Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    randomDamage2: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
  },
};
</script>
<style>
</style>