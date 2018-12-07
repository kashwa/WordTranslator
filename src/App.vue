<template>
  <div id="app">
    <h1>Word Translator.</h1>
    
    <h5>Powered by Vue.js</h5>

    <TranslateForm @formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
  import TranslateForm from './components/TranslateForm'

  export default {
    name: 'App',
    components: {
      TranslateForm
    },
    methods: {
      translateText(text) {
        // alert(text);
      }
    }
  }
</script>

<style>
#app {
  
}
</style>
