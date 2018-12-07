<template>
  <div id="translateform">
    
    <form @submit="formSubmit">
      <input type="text" v-model="textToTranslate" placeholder="Enter a word">
      <input type="submit" value="translate">
    </form>

  </div>
</template>

<script>

  export default {
    name: 'translateform',
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
