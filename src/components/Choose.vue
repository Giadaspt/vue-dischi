<template>
  <div class=" col-3 d-flex align-items-center justify-content-end ">
    <select class="choose  ">
      <option selected>Seleziona il tuo genere musicale</option>
      <option value="">Rock</option>
      <option value="">Pop</option>
      <option value="">Jazz</option>
      <option value="">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Choose',
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import '../assets/style/choose.scss'; 
</style>