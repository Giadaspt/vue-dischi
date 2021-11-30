<template>
  <div class="row">
    <Preview
      v-for="(card, index) in filteredCategories" :key="index"
      :previewShow="card"
    />
  
  </div>
</template>

<script>
import Preview from './Preview.vue';
import axios from 'axios';

export default {
  name: "AllPreview",

  props:{
    choosed: String,
  },

  components: {
    Preview,
  },
  
  data(){
    return {
      preview: [],
      urlAxios: 'https://flynn.boolean.careers/exercises/api/array/music',
      textcategoryChoose:'',
    }
  },

  mounted(){
    this.getApi();
  },

  computed:{
    filteredCategories(){
      if(this.textcategoryChoose === ''){
        return this.preview
      }
      return this.preview.filter( a =>{
        return this.textcategoryChoose === a.genre
        
        // if (this.textcategoryChoose  === a.author){
        //   return this.getAuthor()
        // }
      })
        
    }
  },

  methods: {
    getApi(){
      axios.get(this.urlAxios).then((response) => {
        //console.log(response);
        this.preview = response.data.response;
      })
      .catch((error) =>{
        console.log(error);
      })
    },

        // getAuthor(){
    //   return this.preview.filter(a =>{
    //     if(this.textcategoryChoose  === a.author){
    //       return a.author;
    //     }
    //   })
    // }
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/all-preview.scss";
  
</style>