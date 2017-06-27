<template>
    <div id='app'>
        <img class='logo' src='./assets/electron.png' />
        <img class='logo' src='./assets/vue.png' />
        <img class='logo' src='./assets/webpack.png' />
        <hello></hello>
        <p>
            Here are the docs for
            <a href='#' @click="link('http://electron.atom.io/docs/')">
                Electron</a>,
            <a href='#' @click="link('http://vuejs.org/guide/')">
                Vue 2</a> and
            <a href='#' @click="link('http://webpack.github.io/docs/')">
                Webpack</a>.
            Customize this template as you wish by adding any
            fancy tool you are used to.
        </p>

        <el-button>Default Button</el-button>
        <time-picker></time-picker>
    </div>
</template>

<script>
  import Hello from './components/Hello.vue'
  import TimePicker from './components/TimePicker.vue'
  // With shell.openExternal(url) is how
  // external urls must be handled, not href
  const shell = require('electron').shell
  export default {
    components: {
      Hello,
      TimePicker
    },
    methods: {
      link: (url) => {
        shell.openExternal(url)
      }
    }
  }
</script>

<style>
    html {
        height: 100%;
    }
    body {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        margin: auto;
    }
    #app {
        color: #2c3e50;
        max-width: 600px;
        font-family: Source Sans Pro, Helvetica, sans-serif;
        text-align: center;
    }
    #app a {
        color: #42b983;
        text-decoration: none;
    }
    #app p {
        text-align: justify;
    }
    .logo {
        width: auto;
        height: 100px;
    }
</style>