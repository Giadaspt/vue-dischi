<template>
  <header>
    <div class="row d-flex justify-content-between">
      <div class="logo">
        <img :src="logo" alt="Logo Spotify">
      </div>
      <Choose/>
    </div>
  </header>
</template>

<script>
import Choose from './Choose.vue'
 
export default {
  name: "Header",
  components:{
    Choose,
  },
  
  data(){
    return {
      logo: require("../assets/img/logo-spostify.png")
    }
  }
}
</script>

<style lang="scss" scoped>

  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/header.scss";

</style>