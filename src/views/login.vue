<template>
    <div id="login">
        <h1>Login</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" /><br>
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
<div class="btn-links">
<br>
        <b-button type="button" variant="primary" v-on:click="login()">Login</b-button>
<div class="login-box-links">
  <b-link href="#">Forgot Password</b-link><br>
  <b-link href="/signup">Sign Up</b-link>
  </div>
</div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      input: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    login () {
      if (this.input.username !== '' && this.input.password !== '') {
        if (this.input.username === this.$parent.mockAccount.username && this.input.password === this.$parent.mockAccount.password) {
          this.$emit('authenticated', true)
          this.$router.replace({ name: 'movies' })
        } else {
          console.log('The username and / or  password is incorrect')
        }
      } else {
        console.log('A username and password must be present')
      }
    }
  }
}
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
margin-bottom: 380px;
    }
.btn-links button{
text-align: right;
}
.login-box-links{
text-align: left;
}

</style>
