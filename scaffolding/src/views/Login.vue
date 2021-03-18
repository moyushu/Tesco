<template>
  <div class="login">
    <div :style="bgImg"></div>
  </div>
</template>
<style>
.login * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
<script>
export default {
  data() {
    return {
      bgImg: {
        backgroundImage: "url(../../public/images/bg.jpg)",
        width: "100%",
        height: "400px",
      },
    };
  },
};
</script>