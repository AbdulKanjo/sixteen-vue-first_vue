<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld :deletePerson="deletePerson" :people="people" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios';

export default {
  name: 'home',
  components: {
    HelloWorld: HelloWorld
  },
  data(){
    return {
      people: []
    }
  }, 
  mounted(){
    axios.get('https://swapi.co/api/people')
          .then(res => {
            this.people = res.data.results;
            console.log(this.people);
          })
  },
  methods: {
    deletePerson(ind){
      this.people.splice(ind, 1);
    }
  }
}
</script>
