<template>
  <div class=" col-3 d-flex align-items-center justify-content-end ">
    <select
      v-model="categoryArtist"
      @change="$emit('chooseCategoryArtist', categoryArtist)"
      class="choose" >
      <option >Tutti gli album</option>
      <option>Bon Jovi</option>
      <option>Queen</option>
      <option>Sting</option>
    </select>
  
  </div>
</template>

<script>
export default {
  name: 'ChooseArtist',

  data(){
    return{
      categoryArtist: '',
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import '../assets/style/choose.scss'; 
</style>