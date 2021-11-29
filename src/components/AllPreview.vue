<template>
  <div class="row">
    <Choose  
      @chooseCategory="performCategory"/>
    <Preview
      v-for="(card, index) in filteredCategories" :key="index"
      :previewShow="card"
    />
  
  </div>
</template>

<script>
import Preview from './Preview.vue';
import Choose from './Choose.vue';
import axios from 'axios';

export default {
  name: "AllPreview",

  components: {
    Preview,
    Choose,
  },

  mounted(){
    this.getApi();
  },

  data(){
    return {
      preview: [],
      urlAxios: 'https://flynn.boolean.careers/exercises/api/array/music',
      textcategoryChoose:'',
    }
  },

  computed:{
    filteredCategories(){
      if(this.textcategoryChoose === 'Seleziona il tuo genere musicale'){
        return this.preview
      }
      return this.preview.filter( a =>{
        if (this.textcategoryChoose  === a.genre){
          return a.genre
        } else if (this.textcategoryChoose  === a.author){
          return this.getAuthor()
        }
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

    performCategory(text){
      console.log('io sono text',text);
      this.textcategoryChoose= text;
      this.getApi()
    },

    getAuthor(){
      return this.preview.filter(a =>{
        if(this.textcategoryChoose  === a.author){
          return a.author;
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/all-preview.scss";
  
</style>