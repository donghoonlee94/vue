<template>
  <div>
    <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트(app.vue)의 데이터 이름"></app-header> -->
    <app-header 
      v-bind:propsdata="str"
      v-on:renew="renewStr" 
      ></app-header>
  </div>
</template>

<script>
// 파일의 내용이 AppHeader 라는 변수에 담겼다.
import AppHeader from './components/AppHeader.vue'

// 위의 임포트 방식을 풀어 해석하면 아래와 같다.

 /* var AppHeader = {
  template : '<header><h1>Header</h1></header>'
} */

export default {
  /* 기존은 아래 방식이나, vue에서는 아래와 같은 방식을 하지 않음. 컴포넌트 간의 충돌을 막기 위함. 
  new Vue({
    data: {
      str : ''h1
    }
  }) */
  data: function() {
    return {
      str: 'Header'
    }
  },
  components : {
    'app-header' : AppHeader,
  },
  methods: {
    renewStr: function() {
      this.str = 'hi';
    }
  }
}
</script>

<style>

</style>