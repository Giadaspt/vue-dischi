<template>
  <div class="container-fluid">

    <Header
      @chooseCategory="performCategory" :genreMusicCategory="musicCategory"/>

    <AllPreview
     :selection="categoryChoose"
     @musicGenre="genreMusic"/>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import AllPreview from './components/AllPreview.vue'


export default {
  name: 'App',
  components: {
    Header,
    AllPreview,
  },

  data(){
    return {
      categoryChoose: '',
      musicCategory:[],
    }
  },

  methods:{
    performCategory(text){
      this.categoryChoose = text;
      console.log('io sono app',text);
      console.log( this.categoryChoose);
    },

    genreMusic(genre){
      this.musicCategory = genre
      console.log(genre);
    }
  }
}
</script>

<style lang="scss">

@import './assets/style/vars.scss';
@import './assets/style/general.scss';

</style>
