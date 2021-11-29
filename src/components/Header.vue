<template>
  <header>
    <div class="row d-flex justify-content-between">
      <div class="logo">
        <img :src="logo" alt="Logo Spotify">
      </div>
      <!-- <Choose  
        @chooseCategory="performCategory"
        v-model="category"
        @change="$emit('chooseCategory', category)"/>
      <ChooseArtist
        @chooseCategoryArtist="performCategory"
        v-model="categoryArtist"
        @change="$emit('chooseCategoryArtist', categoryArtist)"/>
      /> -->
    </div>
  </header>
</template>

<script>
// import Choose from './Choose.vue';
// import ChooseArtist from './ChooseArtist.vue';
 
export default {
  name: "Header",
  // components:{
  //   Choose,
  //   ChooseArtist,
  // },
  
  data(){
    return {
      logo: require("../assets/img/logo-spostify.png"),
      category: '',
      categoryArtist:'',
      textcategoryChoose: ''
    }
  },
}
</script>

<style lang="scss" scoped>

  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/header.scss";

</style>