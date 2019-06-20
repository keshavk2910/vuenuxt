<template>
  <nav>
    <ul id="dots">
      <li
        v-for="(slide, slideIndex) in slides"
        :class="{
						'active': slideIndex === activeSlideIndex,
						'subnav': slide.subs && slide.subs.length > 0, 
						[mergeClasses(slide.class)]: true,
					}"
        class="tab"
        v-bind:key="slide.id"
      >
        <div class="wrap">
          <a @click.prevent="handleGoto(index, 0)" :href="getSlideUrl(slide.id)"
          >
            <span class="slidename">{{ slide.name }}</span>
            <span class="dot"></span>
          </a>
        </div>
        <ul v-if="slide.subs && slide.subs.length > 0" class="subdots">
          <li
            v-for="(sub, subIndex) in slide.subs"
            v-bind:key="sub.id"
            v-bind:style="{ display: (showSubItem(subIndex, activeSubIndex, slide) ? 'flex' : 'none') }"
            v-bind:class="mergeClasses(sub.class)"
          >
            <a @click="handleGoto(index, subIndex)">
              <span class="subname">{{ sub.name }}</span>
              <span class="subdot"></span>
            </a>
          </li>
        </ul>
      </li>
    </ul>
  </nav>
</template>
<script>
export default {
  props: ['slides', 'activeSlideIndex', 'activeSubIndex', 'basePush'],
  methods: {
    getSlideUrl(id) {
      return (settings.basePush === '/' ? '/' : settings.basePush+'/')+slide.id+'/';
    },
    handleGoto(slideIndex, subIndex) {
      this.$emit('goto', { slideIndex, subIndex });
    }
  }
};
</script>
<style>
</style>
