<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1 class="md-display-2">{{currUser}}</h1>
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
          <md-input v-model="newUser.username"/>
        </md-field>
        <md-field>
          <label>Email</label>
          <md-input v-model="newUser.email"/>
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
    data() {
      return {
        newUser: {},
        users: [],
        currUser: 'Guest'
      }
    },
    components: {
      // test, users
    },
    methods: {
      login: function () {
        for (let i = 0; i < this.users.length; i++) {
          if (this.newUser.username === this.users[i].username && this.newUser.email === this.users[i].email) {
            this.currUser = 'Welcome ' + this.users[i].name;
            return true;
          }
        }
        return false;
      },
      signup: function () {
      }
    },
    created: function () {
      this.$http.get('https://jsonplaceholder.typicode.com/users')
        .then(function (response) {
          this.users = response.data;
          console.log(response.data);
        });
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

  /*.md-primary {*/
  /*background-color: #448aff;*/
  /*}*/

  /*.md-accent {*/
  /*background-color: #ff5252;*/
  /*}*/
  /*.myclass{*/
  /*background-color: #42b883;*/
  /*!*background-color: #35495e;*!*/
  /*}*/
  .myclass {
    margin-right: 35%;
    margin-left: 35%;
  }
</style>
