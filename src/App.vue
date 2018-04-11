<template>
  <div id="app">
    <h2><b><u>App.vue</u> (Parent)</b></h2>
    <img src="./assets/logo.png">
    <h1>Tentang {{ aboutName }}</h1>
    <input type="text" v-model="aboutName">
    <hr>
    <h2><b><u>About.vue</u> (Child)</b></h2>
    <!-- <About/> adalah cara memanggil komponen About dari './components/About' -->
    <About v-bind:name="aboutName"/> <!-- data name di child(About) disamakan dengan data di parent(App) 
                                      yaitu data aboutName -->
    <!-- Pemanggilan komponen bisa juga melalui pemisah ( - ) -->
    <!-- dengan aturan besarnya, misal FlsBlogSaya.vue maka manggil jadi <fls-blog-saya/> -->
    <hr>
    <h2><b><u>FlsBlog.vue</u> (Child)</b></h2>
    <fls-blog v-for="(article, index) in articles" :key="index"
              :title="article.title"
              :content="article.content"/> <!-- :key berisi sesuatu yg uniq, misal artikel keynya
                                            id_artikel-->
  </div>
</template>

<script>
// untuk memanggil About dari komponen di file terpisah
import About from './components/About'
import FlsBlog from './components/FlsBlog'

export default {
  // set component About
  components:{ About, FlsBlog },

  name: 'app',
  data () {
    return {
      aboutName: 'Hermawan',
      articles: [
        { title: 'Semarang macet', content: 'Wah iya macet sekali in sungguh sungguh' },
        { title: 'Kudus panas', content: 'kudus sanatlah panas' },
        { title: 'Demak berlubang', content: 'di demak banyak lubang' }
      ]
    }
  }
}
</script>

<style>

</style>
