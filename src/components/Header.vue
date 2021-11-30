<template>
  <header>
    <div class="row d-flex justify-content-between">
      <div class="logo">
        <img :src="logo" alt="Logo Spotify">
      </div>
      <div class=" col-3 d-flex align-items-center justify-content-end ">
        <select
          v-model="category"
          @change="$emit('chooseCategory', category)"
          class="choose" >
          <option value="" selected>Tutti gli album</option>
          <option 
          v-for="(category, index) in genreMusicCategory"
          :key="index"
          :value="category">{{category}}</option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>

// import ChooseArtist from './ChooseArtist.vue';
 
export default {
  name: "Header",

  props:{
    genreMusicCategory: Array,
  },
  
  data(){
    return {
      logo: require("../assets/img/logo-spostify.png"),
      category: '',
    }
  },
}
</script>

<style lang="scss" scoped>

  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/header.scss";
  @import "../assets/style/choose.scss";

</style>