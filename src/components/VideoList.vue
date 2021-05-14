<template>

<ul class="list-group col-md-6 p-3">
    <VideoItem 
    v-for="video in videos" 
    :video="video" 
    v-bind:key="video.id"
    @videoselect="selectvideo"/>
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
    },
    methods:{
        selectvideo(video){
            this.$emit("videoselect",video)
        }
    }
}

</script>


<style>

</style>