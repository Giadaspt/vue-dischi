<template>
  <div>
    <select class="col-3 choose" >
      <option selected>Seleziona un genere musicale</option>
      <option value="">Rock</option>
      <option value="">Metal</option>
      <option value="">Pop</option>
      <option value="">Jazz</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Choose",
}
</script>

<style lang="scss" scoped>
@import "../assets/style/choose.scss";

</style>