<template>

<ul>
    <h3>Video List</h3>
    <VideoItem/>
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