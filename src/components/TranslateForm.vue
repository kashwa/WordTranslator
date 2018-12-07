<template>
  <div class="row" id="translateform">
    <div class="col-md-6 col-md-offset-3">
      <form id="transform" class="form-inline well" @submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word">
        <select class="form-control" v-model="lang">
          <option value="ru">Russian</option>
          <option value="es">Spanish</option>
          <option value="ar">Arabic</option>
          <option value="fr">French</option>
        </select>

        <input class="btn btn-primary" type="submit" value="translate">
      </form>
    </div>
  </div>
</template>

<script>

  export default {
    name: 'translateform',
    data() {
      return {
        textToTranslate: '',
        lang: ''
      }
    },
    created() {
      this.lang = 'es'
    },
    methods: {
      formSubmit(e) {
        this.$emit('formSubmit', this.textToTranslate, this.lang);
        e.preventDefault();
      }
    }
  }
</script>

<style>
  #transform {
    border-radius: 10px;
    border: 1px #ccc solid;
  }
  select, input {
    margin-left: 10%;
  }
  h5 {
    margin-bottom: 5%;
  }
</style>
