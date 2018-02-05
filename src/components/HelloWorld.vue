<template>
  <div class="HelloWorld">
    <h1 class="title is-1" v-on:click.once="dothis">{{msg}}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    dothis: function (event) {
      console.log('clicked')
    }
  }
}
</script>
