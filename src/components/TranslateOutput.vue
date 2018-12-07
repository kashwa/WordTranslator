<template>
  <h2>{{ translatedText }}</h2>
</template>

<script>

  export default {
    name: 'translateOutput',
    props: ['translatedText'],
    data() {
      return {
        textToTranslate: ''
      }
    },
    methods: {
      formSubmit(e) {
        this.$emit('formSubmit', this.textToTranslate);
        e.preventDefault();
      }
    }
  }
</script>

<style>

</style>
