<template>
  <div class="dirDiv" v-for="(person, index) in people" :key="index">
    {{index+1}}. name: {{person.name}}
    <br>
    age: {{person.age}}
    <br>
    nickname: {{person.nickname}}
  </div>
</template>

<script>
// @ is an alias to /src
import trying from '/data/trying.json'

export default {
  name: 'HomeView',
  components: {
  },
  data (){
   return {
     people: trying.people
   }
  },
  mounted () {

  }
}
</script>

<style scoped>
.dirDiv{
  direction: ltr;
  text-align: left;
  margin-left: 5rem;
  margin-bottom: 1rem;
}
</style>
