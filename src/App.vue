<template>
 <div id="app">
  <NavBlock/>
  <Form/>
 </div>
</template>

<script>
import Form from './components/Form.vue'
import NavBlock from './components/NavBlock.vue'

export default {
 name: "App",
 data() {
  return {};
 },
 components: {
   Form,
   NavBlock
 }
};
</script>

<style>
html, body, #app{
  height: 100%;
}
* {
 box-sizing: border-box;
}

body {
 background-color: #1e1e36;
}

body,
p,
a,
ul,
li,
h1,
h2,
h3 {
 margin: 0;
 padding: 0;
}
a{
  text-decoration: none;
  color: inherit;
}
li {
 list-style: none;
}

svg{
  fill: #a9a9ab;
}

#app {
  height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
 width: 95%;
 margin: 0 auto;
 font-family: Avenir, Helvetica, Arial, sans-serif;
 -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
 color: #fff;
}
</style>
