<template>
  <div class=" col-3 d-flex align-items-center justify-content-end ">
    <select
      v-model="category"
      @click="$emit('chooseCategory', category)"
      class="choose">
      <option selected >Seleziona il tuo genere musicale</option>
      <option>Rock</option>
      <option>Pop</option>
      <option>Jazz</option>
      <option>Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Choose',

  data(){
    return{
      category: '',
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