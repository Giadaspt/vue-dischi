<template>
  <div class="container">
    <Header/>
    <All-Preview/>
  </div>
</template>

<script>
import AllPreview from './components/AllPreview.vue'
// import axios from "axios";
import Header from "./components/Header.vue"

export default {
  name: 'App',
  components: {
    Header,
    AllPreview,
    // axios
  }
}
</script>

<style lang="scss">

@import './assets/style/vars.scss';
@import './assets/style/general.scss';

</style>
