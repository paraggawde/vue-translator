<template>
  <div id="app" class="text-center">
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>Vue Translator</h2>
    <h3>A simple Translator app with Vue.js</h3>
    <TranslateForm v-on:formSubmit="translateText"/>
    <br>
    <VueTranslate v-text="translatedText"/>
  </div>
</template>

<script>
import TranslateForm from "./components/TranslateForm.vue";
import VueTranslate from "./components/VueTranslate.vue";

export default {
  name: "app",
  components: {
    TranslateForm,
    VueTranslate
  },
  data: function(){
    return{
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text, selectLanguage) {
      this.$http.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180905T173611Z.47c93f1095f3165b.3ccd6e6ce6d66b5db0e7b2bedfa3abbe979eaf54&lang="+selectLanguage+"&text=" +
          text).then((response) => {
            this.translatedText = response.body.text[0];
          });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100px;
}
img{
  height: 100px;
}
</style>
