<template>
  <div class="hello">
    <h1 
    v-if="showing"
    v-bind:title="msg">
    <span v-if="err">{{fail}}</span>
    give me the {{item.foodName}}
    </h1>
    <input type="text" v-model="msg" @keyup.enter="getItem()">
    <button v-on:click="getItem">Add grapes</button>

  </div>
</template>

<script>
export default {
  name: 'MyList',
  data() {
    return {
      msg: '',
      fail: 'NO! I dont want that!',
      err: false,
      showing: true,
      foods: [
        {foodId: 1, foodName: 'pumpkin'},
        {foodId: 2, foodName: 'melon'},
        {foodId: 3, foodName: 'pie'},
        {foodId: 4, foodName: 'cheese'},
        {foodId: 5, foodName: '*#*+11?~~'},
        {foodId: 7, foodName: 'bread'},
        {foodId: 8, foodName: 'water'},
        {foodId: 9, foodName: 'apple'},
        {foodId: 10, foodName: 'samsung'},
        {foodId: 11, foodName: 'pain'},
        {foodId: 12, foodName: 'Multivitaminsaft'},
        {foodId: 13, foodName: 'AK-47'},
        {foodId: 14, foodName: 'dogfood'},
        {foodId: 15, foodName: 'pikachu'},
        {foodId: 16, foodName: 'tiramisu'},
        {foodId: 17, foodName: 'artischocken'},
        {foodId: 18, foodName: 'aloavera'},
        {foodId: 19, foodName: 'pinzette'}
      ],
      item: []
    }
  },
  methods: {
    getItem(){
      if(this.msg == this.item.foodName){
        let rand = Math.floor(Math.random() * this.foods.length)
        this.item = this.foods[rand]
        this.err = false
      }else{
        this.err = true;
      }

      this.msg = ''
    }
  },
  mounted(){
    let rand = Math.floor(Math.random() * this.foods.length)
    this.item = this.foods[rand]
  }
}
</script>

<style scoped>
h1{
  background-color: whitesmoke;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
