<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">ID:</label>
      <input id="username" type="text" v-model="username" />
    </div>
    <div>
      <label for="password">PW:</label>
      <input id="password" type="password" v-model="password" />
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from "axios";


export default {
  data: function() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    submitForm: function() {
      // eslint-disable-next-line no-console
      console.log(this.username, this.password);
      var url = "https://jsonplaceholder.typicode.com/users";
      const data = {
        username: this.username,
        password: this.password
      };
      axios
        .post(url, data)
        .then(function(response) {
          // eslint-disable-next-line no-console
          console.log(response);
        })
        .catch(function(error) {
          // eslint-disable-next-line no-console
          console.log(error);
        });
    }
  }
};
</script>

<style>
</style>
