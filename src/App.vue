<template>
  <div class="container-fluid">
    <Header/>
    <All-Preview/>
  </div>
</template>

<script>
import AllPreview from './components/AllPreview.vue'
import Header from './components/Header.vue'


export default {
  name: 'App',
  components: {
    Header,
    AllPreview,
  }
}
</script>

<style lang="scss">

@import './assets/style/vars.scss';
@import './assets/style/general.scss';

</style>
