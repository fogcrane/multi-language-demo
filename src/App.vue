<template>
  <div id="app">
    <img src="./assets/logo.png">

    <h1>{{ $t('helloWorld') }}</h1>
    <el-button type="primary" @click="toggleLanguage">{{ $t('toggleLang') }}</el-button>
    <!-- <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul> -->
  </div>
</template>

<script>
import Cookies from 'js-cookie';
export default {
  name: 'app',
  data() {
    return {
      langType: 'zh',
    }
  },
  methods: {
    toggleLanguage() {
      if (Cookies.get('language') === 'zh') {
        this.langType = 'en';
        Cookies.set('language', 'en');
        window.location.reload();
      } else if (Cookies.get('language') === 'en') {
        this.langType = 'zh';
        Cookies.set('language', 'zh');
        window.location.reload();
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

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
