<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="input-wrapper">
      <component-input v-model="value"></component-input>
    </div>
  </div>
</template>

<script>
import componentInput from './input.vue';
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      value: ''
    }
  },
  watch: {
    value(val) {
      console.log(val);
    }
  },
  components: {
    componentInput
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
.input-wrapper {
  margin-left: 50%;
  transform: translate(-50%, 0);
  width: 300px;
  height: 100px;
  /* background-color: pink; */
}
</style>
