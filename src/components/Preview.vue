<template>
  <div class="col-2 preview m-3 p-3">
    <img :src="previewShow.poster" :alt="previewShow.title">
    <h6>{{previewShow.title}}</h6>
    <p>{{previewShow.author }}</p>
    <p>{{previewShow.year }}</p>
  </div>
</template>

<script>
export default {
  name: "Preview",

  props: {
    previewShow: Object,
  }
}
</script>

<style lang="scss" scoped>
 @import "../assets/style/vars.scss";
  @import '../assets/style/mixins.scss';
  @import "../assets/style/general.scss";
  @import "../assets/style/preview-card.scss";
</style>