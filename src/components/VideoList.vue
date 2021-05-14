<template>

<ul class="list-group">
    <VideoItem v-for="video in videos" :video="video" v-bind:key="video.id"/>
</ul>

</template>


<script>

import VideoItem from "./VideoItem.vue"

export default{
    name: "VideoList",
    components:{
        VideoItem
    },
    props:{
        videos:Array
    }
}

</script>


<style>

</style>