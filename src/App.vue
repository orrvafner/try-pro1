<template>
<div id="content" ref="appView">
    <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/> 
</div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
   return{

   };
  },
  mounted() {
    this.resizeHandler();
    window.addEventListener("resize", this.resizeHandler);
  },
  unmounted() {
    window.removeEventListener("resize", this.resizeHandler);
  },
  methods: {
    resizeHandler() {
      let width= window.innerWidth
      let height= window.innerHeight

      if(!(width <= 600 && height <= 1000 && (height/width) <= 2.5 && (height/width) >= 1.5)) {
        this.$refs.appView.style.height = `${Math.min(height, (width*2))}px`
        this.$refs.appView.style.width = `${Math.min(width, (height*0.5))}px`
      }

        this.$refs.appView.style.margin = `auto`
    },
  },
})
</script>


<style>

/* css variables */
:root {
  --big-bg-color: pink;
  --content-color: #f9f1f1;
  --font-color: #2c3e50;
  --chosen-font-color: #ffb4b4;
}

@media(prefers-color-scheme: dark){
  :root {
    --big-bg-color-dark: pink;
    --content-color-dark: #2c3e50;
    --font-color-dark: pink;
    --chosen-font-color--dark: red;
  }
}

@media(prefers-color-scheme: light){
  :root {
    --big-bg-color-light: pink;
    --content-color-light: #f9f1f1;
    --font-color-light: #2c3e50;
    --chosen-font-color--light: #ffb4b4;
  }
}

/* main css */

* {
  direction: rtl;
  text-align: start;
  user-select: none;
  text-align: center;
  color: var(--font-color);
}

html,
body {
  height: 100vh;
  width: 100vw;
  scroll-behavior: smooth;
  overflow: hidden;
}

html {
  display: table;
  margin: auto;
}

body {
  position: relative;
  vertical-align: middle;
  background-color: var(--big-bg-color);
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
  font-size: 1.5rem;
  font-weight: 500;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var( --font-color);
  user-select: none;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: var( --font-color);
}

nav a.router-link-exact-active {
  color: var(--chosen-font-color);
}

#content {
  display: block;
  height: 100%;
  width: 100%;
  background-color: var(--content-color);
}
</style>
