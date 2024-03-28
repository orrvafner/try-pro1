<template>
  <div class="swatchers">
    <span @click="changeColor($event)" style="background: #222;"></span>
    <span @click="changeColor($event)" style="background: #f76262;"></span>
    <span @click="changeColor($event)" style="background: #3e84da;"></span>
    <span @click="changeColor($event)" style="background: #ebb332;"></span>
  </div>
  <button class="theme">dark mode</button>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<script>

export default {
  name: 'HomeView',

  data (){
   return {
   }
  },
  methods : {
    changeColor(e){
      app.style.setProperty('--content-color', e.target.style.background);
    },
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

.swatchers span {
  display: inline-block;
  width: 1rem;
  height: 1rem;
  margin: 0.5rem;
  cursor: pointer;
}
</style>
