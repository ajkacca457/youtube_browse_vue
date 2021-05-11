<template>

<ul>
    <VideoItem />
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