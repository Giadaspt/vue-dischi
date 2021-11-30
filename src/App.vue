<template>
  <div class="container-fluid">

    <Header
      @chooseCategory="performCategory"/>

    <All-Preview
     :choosed="textcategoryChoose"/>

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
  },

  data(){
    return {
      textcategoryChoose: '',
    }
  },

  methods:{
    performCategory(text){
      console.log('io sono app',text);
      this.textcategoryChoose = text;
    },
  }
}
</script>

<style lang="scss">

@import './assets/style/vars.scss';
@import './assets/style/general.scss';

</style>
