<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ msg2 }}</h2>
    <input type="text" v-model="msg">
    <p>
      <router-link to='/PageA'>PageA</router-link>
      <router-link :to="'/PageB/' + msg ">PageB</router-link>
    </p>
    <hr>
    <form-a />
    <form-b />
    <hr>
    <form-a />
    <hr>
    <h2>{{ msg3 }}</h2>
    <span>Selected: {{ selectedComponent }}</span><br>
    <input type="radio" id="FormA" value="FormA" v-model="selectedComponent">
    <label for="FormA">FormA</label>
    <input type="radio" id="FormB" value="FormB" v-model="selectedComponent">
    <label for="FormB">FormB</label>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
    <hr>
  </div>
</template>

<script>
import FormA from './FormA.vue'
import FormB from './FormB.vue'
export default {
  name: 'HelloWorld',
  components: {
    FormA,
    FormB
  },
  data () {
    return {
      msg: 'これはテストだからー',
      msg2: 'こんにちは、世界',
      msg3: '動的なコンポーネント',
      selectedComponent: ''
    }
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
</style>
