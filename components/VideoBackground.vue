<template>
  <div class="vidwrap">
    <video id="home-hero-video" width="100%" height="auto" preload autoplay muted playsinline loop>
      <source src="/homemob.mp4" type="video/mp4" media="all and(max-width:600px)">
      <source src="/home.mp4" type="video/mp4">
    </video>
    <div class="vidshader"></div>
  </div>
</template>
<script>
export default {
    
}
</script>
