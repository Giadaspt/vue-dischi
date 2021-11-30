<template>
  <div class=" col-3 d-flex align-items-center justify-content-end ">
    <select
      v-model="categoryArtist"
      @change="$emit('chooseCategoryArtist', categoryArtist)"
      class="choose" >
      <option value="" selected>Tutti gli album</option>
      <option value="Bon Jovi">Bon Jovi</option>
      <option value="Queen">Queen</option>
      <option value="Sting">Sting</option>
      <option value="Steve Gadd Band">Steve Gadd Band</option>
      <option value="Iron Maiden">Iron Maiden</option>
      <option value="Eric Clapton">Eric Clapton</option>
      <option value="Deep Purple">Deep Purple</option>
      <option value="Metallica">Metallica</option>
      <option value="Dave Weckl">Dave Weckl</option>
      <option value="Michael Jacjson">Michael Jacjson</option>
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