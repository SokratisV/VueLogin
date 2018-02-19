<template>
  <div id="app">
    <img src="./assets/logo.png">
    <br>
    <md-card class="myclass">
      <md-card-header>
        <div class="md-title">
          Login with Vue-material.
        </div>
      </md-card-header>
      <md-card-content>
        <md-field>
          <label>Username</label>
          <md-input v-model="user"/>
        </md-field>
        <md-field>
          <label>Email</label>
          <md-input v-model="email"/>
        </md-field>
      </md-card-content>
    </md-card>
    <md-button class="md-raised md-primary" v-on:click="login()">Login</md-button>
    <md-button class="md-raised md-accent" v-on:click="signup()">Sing up</md-button>
    <!--<users></users>-->
  </div>
</template>

<script>
  import test from './components/test'
  import users from './components/users'

  export default {
    name: 'App',
    components: {
      // test, users
    },
    methods: {
      login: function () {
        alert('logging in');
      },
      signup: function () {
        alert('signing up');
      }
    }
  }
</script>

<style>
  #app {
    text-align: center;
    margin-top: 60px;
    margin-left: 30px;
    margin-right: 30px;
  }

  .md-primary {
    background-color: #448aff;
  }

  .md-accent {
    background-color: #ff5252;
  }
  .myclass{
    background-color: #42b883;
    /*background-color: #35495e;*/
  }
  .myclass{
    margin-right: 35%;
    margin-left: 35%;
  }
</style>
