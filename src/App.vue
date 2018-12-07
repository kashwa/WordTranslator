<template>
  <div class="text-center" id="app">
    <h1>Word Translator.</h1>
    
    <h5 class="text-muted">Powered by Vue.js</h5>

    <TranslateForm @formSubmit="translateText"></TranslateForm>

    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
  import TranslateForm from './components/TranslateForm'
  import TranslateOutput from './components/TranslateOutput'

  export default {
    name: 'App',
    components: {
      TranslateForm,
      TranslateOutput
    },
    data: function () {
      return {
        translatedText: '',
      }
    },
    methods: {
      translateText(text, lang) {
        this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181207T073908Z.0a30ad49bc66a9e1.b14670e2e0c57468b2780be6bdbd02d74d5672b9&lang='+lang+'&text=' + text)
        .then((response) => {
          this.translatedText = response.body.text[0];
        })
      }
    }
  }
</script>

<style>
body {
  background: #fefefe;
}
</style>
