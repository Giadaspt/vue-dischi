<template>
  <div class="row">

    <Preview
      v-for="(card, index) in preview" :key="index"
      :previewShow="card"
    />
  
  </div>
</template>

<script>
import Preview from './Preview.vue'
import axios from 'axios';

export default {
  name: "AllPreview",

  components: {
    Preview,
  },

  mounted(){
    this.getApi();
  },

  data(){
    return {
      preview: [],
      // urlAxios: 'https://flynn.boolean.careers/exercises/api/array/music',
    }
  },

  methods: {
    getApi(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
        console.log(response);
        this.preview = response.data.response;
      })
      .catch((error) =>{
        console.log(error);
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