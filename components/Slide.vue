<template>
    <div>
        <div class="slide" v-html="slideHtml"></div>
        <div class="subs">
            <Sub v-for="(sub, index) in subs" v-bind:key="sub.id" :data="sub" :index="index">
        </div>
    </div>
</template>
<script>
export default {
    created() {

    }
}
</script>
<style>

</style>
