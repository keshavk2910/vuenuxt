<template>
    <div id=frame>
        <!-- <Preload />
		<VideoBackground /> -->
		<div>		
			<Slide v-for="slide in slides" :id="slide.id" v-bind:key="slide.id" />
		</div>
		<div id=back @click="goNext(LEVEL_SUB)"><img src=back.svg />{{settings.backText}}</div>
		<div id=next @click="goPrev(LEVEL_SUB)"><img src=next.svg />{{settings.nextText}}</div>
		<!-- <LangSwitch />
		<a href="/" :data-current="$store.state.id" :data-currentsub="$store.state.currentSub" id=logo :data-postopen="$store.state.modal"></a> -->
		<Timeline :slides="slides" />
		<!-- <div id=explore>
			<ul id=menu>
				<li v-for="(slide,index) in $store.state.allslides" v-bind:key="slide.id"><a :class="{'active':index===$store.state.current}" @click=tab($event,false) :data-slide="slide.id" class=tab>{{ slide.name }}</a></li>
			</ul>
			<div id="menu_footer">© 2019 Haiti Takes Root™ | All Rights Reserved | <a href="https://www.starmenusa.com">Making Brands Work™</a></div>
			<img id=flower src=/flower.svg />
			<img id=close src=/close.svg @click="nomob" />
		</div>
		<div id=modal>
		</div> -->
	</div>
</template>
<script>
import Timeline from './Timeline';

const LEVEL_SLIDE = 1;
const LEVEL_SUB = 2;
const LEVEL_SUBMODAL = 3;

export default {
    props: ['settings'],
    components: {
        Timeline,
    },
    computed: {
        slides() {
            return this.settings.nav;
        },
    },
    methods: {
        goNext(level) {

        },
        goPrev(level) {

        }
    }
}
</script>
<style>

</style>
