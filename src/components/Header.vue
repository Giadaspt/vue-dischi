<template>
  <header>
    <div class="row d-flex ">
      <div class="logo">
        <img :src="logo" alt="Logo Spotify">
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",

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