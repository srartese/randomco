<template>
  <div class="attract">
    <video autoplay muted loop id="backgroundVideo">
      <source src="../assets/screensaver.mp4" type="video/mp4">
    </video>
  </div>
</template>

<script>
export default {
  name: 'Attract',
  data () {
    return {
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #backgroundVideo {
    position: fixed;
    right: 0;
    bottom:0;
    z-index: 1;
    min-width: 100%;
    min-height: 100%;
  }

</style>
