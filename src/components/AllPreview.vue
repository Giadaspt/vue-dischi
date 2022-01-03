<template>
  <div class="row">
    <Preview
      v-for="(card, index) in filteredCategories" :key="index"
      :previewShow="card"/>
  </div>
</template>

<script>
import Preview from './Preview.vue';
import axios from 'axios';

export default {
  name: "AllPreview",

  props:{
    selection: String,
    select: String,
  },

  components: {
    Preview,
  },
  
  data(){
    return {
      preview: [],
      urlAxios: 'https://flynn.boolean.careers/exercises/api/array/music',
      genreCategory: [],
      genreArtist: [],
    }
  },

  mounted(){
    this.getApi();
  },

  computed:{
    filteredCategories(){
      if(this.selection === '' && this.select === '' ){
        return this.preview;
      }
      return this.preview.filter( a =>{
        let genre = a.genre  === this.selection;
        let author = a.author === this.select;
        let all = genre + author;

        return all ;
    
      })
        
    },
  },

  methods: {
    getApi(){
      axios.get(this.urlAxios).then((response) => {
        //console.log(response);
        this.preview = response.data.response;

        this.preview.forEach(a =>{
          if(!this.genreCategory.includes(a.genre)){
            this.genreCategory.push(a.genre);
          } 

          if (!this.genreArtist.includes(a.author)){
            this.genreArtist.push(a.author);
          }
        })

        this.$emit('musicGenre', this.genreCategory);
        this.$emit('musicArtist', this.genreArtist);
         
      })
      .catch((error) =>{
        console.log(error);
      })
    },
  },
  //   getApiArtist(){
  //     axios.get(this.urlAxios).then((response) => {
  //       //console.log(response);
  //       this.preview = response.data.response;

  //       this.preview.forEach(e => {
  //         if(!this.genreArtist.includes(e.author)){
  //           this.genreArtist.push(e.author)
  //         }
  //       })
 
  //       this.$emit('musicArtist', this.genreArtist);
  //     })
  //     .catch((error) =>{
  //       console.log(error);
  //     })
  // },
} 

</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/all-preview.scss";
  
</style>