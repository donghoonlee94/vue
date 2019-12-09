<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password"> 
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
/* eslint-disable no-console */
// 데이터를 주고 받기 위한 통신 라이브러리 axios 
// response는 요청 후 응답, catch는 에러.
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    submitForm: function() {
      //event.preventDefault();
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users'
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data)
        .then(function(response){
          console.log(response);
        })
        .catch(function(error){
          console.log(error);
        });
    }
  }
}
</script>

<style>

</style>