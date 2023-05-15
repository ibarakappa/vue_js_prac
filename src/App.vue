<script>
export default {
   data() {
      return {
         a: 1,
         temp: null,
         person: [
            {
               name: "Wilson",
               age: 23,
            },
            {
               name: "Mary",
               age: 20,
            },
         ],
         arrMeal: "",
         isShow: true,
      };
   },
   methods: {
      changeAValue() {
         this.a = this.temp;
      },
      switchA() {
         console.log("A");
         this.isShow = !this.isShow;
      },
   },
   mounted() {},
};
</script>

<template>
   <div class="text-area">
      <h1>V-model</h1>
      <h2>a : {{ a }}</h2>
      <p class="text-primary">tem : {{ temp }}</p>
      <!-- input與temp雙向綁定 -->
      <input type="password" v-model="temp" title="A" />
      <!-- v-on:click等同事件監聽 -->
      <!-- 點下按鈕會觸發changeAValue -->
      <button type="button" class="btn btn-primary" v-on:click="changeAValue">
         update
      </button>
      <label for="breakfast">早餐</label>
      <input
         id="breakfast"
         type="checkbox"
         value="breakfast"
         v-model="arrMeal"
      />
      <label for="lunch">中餐</label>
      <input id="lunch" type="checkbox" value="lunch" v-model="arrMeal" />
      <label for="dinner">晚餐</label>
      <input id="dinner" type="checkbox" value="dinner" v-model="arrMeal" />
      <p>{{ arrMeal }}</p>
   </div>
   <div class="area2">
      <h1>V-if</h1>
      <button type="button" v-on:click="switchA">switch</button>
      <p>{{ isShow }}</p>
      <p v-if="isShow">True</p>
      <p v-else>False</p>
   </div>

   <ul>
      <li v-if="arrMeal == 'breakfast'">breakfast</li>
      <li v-else-if="arrMeal == 'lunch'">lunch</li>
      <li v-else-if="arrMeal == 'dinner'">dinner</li>
   </ul>
</template>

<style scoped>
.text-area {
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   
}
</style>
