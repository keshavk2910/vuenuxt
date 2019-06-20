<template>
  <div id="ex" :data-postopen="$store.state.modal">
    <div id="flags">
      <a href="/">
        <img src="flag_us.jpg">
      </a>
      <a href="/fr">
        <img src="flag_fr.jpg">
      </a>
      <a href="/cr">
        <img src="flag_cr.jpg">
      </a>
    </div>
    <h4
      @click="mob"
      :data-current="$store.state.id"
      :class="'sub_'+$store.state.currentSub"
    >{{settings.exploreText}}</h4>
    <a
      id="burger"
      @click="mob"
      :data-current="$store.state.id"
      :class="'sub_'+$store.state.currentSub"
    ></a>
  </div>
</template>
<script>
export default {
    
}
</script>

