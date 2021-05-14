<template>
<div class="display card p-2  col-md-6" v-if="video">
    <iframe width="100%" height="400" :src="videoUrl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    <div class="detail my-3">
    <h4 @click="display">{{video.snippet.title}}</h4>
    <p>{{video.snippet.description}}</p>
    <h5>{{video.snippet.channelTitle}}</h5>
     <pre>{{video.snippet.publishTime}}</pre>
    </div>
    </div>
</template>


<script>

export default{
    name:"VideoDisplay",
    props: ["video"],
    methods:{
        display(){
            console.log(this.video)

        }
    },
    computed : {
        videoUrl(){
            const videoId=this.video.id.videoId;
            return `https://www.youtube.com/embed/${videoId}`
        }
    }
}

</script>


<style scoped>

</style>