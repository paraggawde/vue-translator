<template>
  <div id="translateForm" class="text-center">
      <form v-on:submit="formSubmit" class="row justify-content-center">
          <div class="col-md-4">
               <input type="text" v-model="inputText" placeholder="Enter a word" class="col-md-4 offset-md-1">
          <select v-model="selectLanguage" class="btn btn-light dropdown-toggle col-md-4 offset-md-1">
              <option value="fr">French</option>
              <option value="ru">Russian</option>
              <option value="es">Spanish</option>
              <option value="it">Italian</option>
              <option value="de">German</option>
              <option value="sv">Swedish</option>
          </select>
          <br>
          <br>
          <input type="submit" value="Translate" class="btn btn-primary col-md-4 offset-md-1">
          </div>
      </form>
  </div>
</template>
<script>
export default {
  name: "TranslateForm",
  data() {
    return {
      inputText: "",
      selectLanguage: ""
    };
  },
  created() {
    this.selectLanguage = "fr";
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit", this.inputText, this.selectLanguage);
      e.preventDefault();
    }
  }
};
</script>

<style>
#translateForm {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-lg-4oothing: antialiased;
  -moz-osx-font-lg-4oothing: grayscale;
  text-align: center;
  rowor: #2c3e50;
  margin-top: 60px;
  height: 100px;
}
</style>
