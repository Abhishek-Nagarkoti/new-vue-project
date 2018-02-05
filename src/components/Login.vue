<template>
  <div class="Login">
    <div class="animated fadeIn container tingle-content-wrapper">
      <h1 class="title is-1">{{msg}}</h1>
      <div class="columns is-mobile">
        <div  class="column is-half">
          <div class="hero is-fullheight">
            <div class="hero-body">
              <div class="tile">
                <div class="tile is-parent is-vertical">
                  <div class="tile is-child box">
                    <form v-on:submit.once="onSubmit">
                      <label class="label">Name</label>
                      <div class="control">
                        <input class="input" style type="text" placeholder="Type name" v-model="name" />
                      </div>
                      <label class="label">Job</label>
                      <div class="control">
                        <input class="input" style type="text" placeholder="Type job" v-model="job" />
                      </div>
                      <button type="submit" class="button is-primary is-fullwidth">Login</button>
                    </form>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div  class="column is-half">
          <div class="hero is-fullheight">
            <div class="hero-body">
              {{ someData }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      msg: 'Welcome to Your Login App',
      name: '',
      job: '',
      someData: ''
    }
  },
  methods: {
    onSubmit: function (event) {
      event.preventDefault()
      this.$http.post('https://reqres.in/api/users', {'name': this.name, 'job': this.job}).then(response => {
        // get body data
        this.someData = response.body
      }, response => {
        // error callback
      })
    }
  }
}
</script>
