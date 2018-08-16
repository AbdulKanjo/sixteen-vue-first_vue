<template>
  <div class="hello">
    <!-- <h1>{{ people }}</h1> -->
    <div :key="ind" v-for="(person, ind) in people">
      <span @click="addPerson(ind)">
        {{person.name}}

      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    people: {
      type: Array,
      default: []
    },
    deletePerson: Function
  },
  data(){
    return {
      me: {
         name: 'Shea',
         age: 35,
         location: 'Dallas',
         favFood: {
           name: "Pizza",
           ingredients: {
             peperoni: true
           }
         }
      },
      addPerson(){
        console.log('Hello@');
      }
    }
  },
  watch:{
    "me.favFood.ingredients.pepperoni": () =>{
      
    }
  },

  // props: ['msg']
  created(val){
    console.log('val: ', val);
    console.log(this);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
