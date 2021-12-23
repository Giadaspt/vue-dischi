<template>
  <div class="container-fluid">

    <Header
      :genreMusicCategory="musicCategory"
      :genreArtistCategory="musicArtistCategory"
      @chooseCategory="performCategory" 
      @chooseCategoryArtist="performCategoryArist"/>

    <AllPreview
      :selection="categoryChoose"
      :select="categoryArtist"
      @musicGenre="genreMusic"
      @musicArtist="artistMusic"/>

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
      categoryArtist: '',
      musicCategory:[],
      musicArtistCategory:[],
    }
  },

  methods:{
    performCategory(text){
      this.categoryChoose = text;
      console.log('io sono app',text);
      console.log( this.categoryChoose);
    },
    performCategoryArist(text){
      this.categoryArtist = text;
      console.log('io sono app',text);
      console.log( this.categoryArtist);
    },

    genreMusic(genre){
      this.musicCategory = genre;
      console.log(genre);
    },

    artistMusic(author){
      this.musicArtistCategory = author;
      console.log(author);
    }
  }
}
</script>

<style lang="scss">

@import './assets/style/vars.scss';
@import './assets/style/general.scss';

</style>
