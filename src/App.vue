<script>
  export default {
    data() {
      return {
        a : 1,
        temp : 0,
        arrMeal : "",
        isShow : true
      };
    },
    methods: {
      changeAValue() {
        this.a = this.temp;
      },

      switchBoo() {
        this.isShow = !this.isShow;
      }
    },
    mounted() {

    }  
  }
</script>

<template>
  <!-- <h2>a : {{ a }}</h2>
  <p class="text-primary">temp : {{ temp }}</p>
  <input type="number" v-model="temp">
  <button class="bg-primary" type="button" v-on:click="changeAValue">update</button> -->

  <label for="breakfast">早餐</label>
  <input id="breakfast" type="radio" value="breakfast" v-model="arrMeal">

  <label for="lunch">中餐</label>
  <input id="lunch" type="radio" value="lunch" v-model="arrMeal">

  <label for="dinner">晚餐</label>
  <input id="dinner" type="radio" value="dinner" v-model="arrMeal">

  <p>{{ arrMeal }}</p>

  <button type="button" v-on:click="switchBoo">switch</button>
  
  <div v-if="isShow" class="box bg-primary"></div>
  <div v-else class="box bg-secondary"></div>

  <ul>
    <li v-if="arrMeal == 'breakfast'">早餐</li>
    <li v-else-if="arrMeal == 'lunch'">午餐</li>
    <li v-else-if="arrMeal == 'dinner'">晚餐</li>
  </ul>
</template>

<style lang="scss" scoped>
  .box {
    width: 50px;
    height: 50px;
  }
</style>
