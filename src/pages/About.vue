<template>
  <div class="about">
    <navtab :cur="1"></navtab>
  </div>
</template>
<script>
import Navtab from "../components/navtab";
export default {
  name: "About",
  components: {
      Navtab
  }
};
console.log(222);
</script>

<style lang="scss" scoped>
</style>