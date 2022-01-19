<template>
  <div class="hello">
    <h2>{{ msg }}</h2>
    <p>Check out the <code>README.md</code> file for additional instructions!</p>
    <h3>New to Vue?</h3>
    <p>Here are some helpful links to get you started</p>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://vuejs.org/v2/style-guide/" target="_blank" rel="noopener">vue style guide</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Adding "scoped" attribute here limits CSS to this component only -->
<style scoped>
h2 {
  margin-top: 40px;
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
