<template>
  <div class="users">
    <h1>Login</h1>
    <form v-on:submit="login">
      <input type="text" v-model="newUser.username" placeholder="Enter Username">
      <br>
      <input type="text" v-model="newUser.email" placeholder="Enter Email">
      <br>
      <input type="submit" value="Login">
    </form>
    <!--<ul>-->
      <!--<li v-for="user in users">-->
      <!--</li>-->
    <!--</ul>-->
  </div>
</template>

<script>
  export default {
    username: 'users',
    data() {
      return {
        newUser: {},
        users: []
      }
    },
    methods: {
      login: function (e) {
        e.preventDefault();
        for (let i = 0; i < this.users.length; i++) {
          if (this.newUser.username === this.users[i].username && this.newUser.email === this.users[i].phone) {
            alert('login successful');

            return true;
          }
        }
        alert('login failed');
        return false;
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

<style scoped>
  .contacted {
    text-decoration: line-through;
  }

</style>
