<template>

<li class="list-group-item my-2 border-1 rounded item">
<div class="media">
  <img class="mr-3" :src="thumbNail" alt="Generic placeholder image" >
  <div class="media-body mt-2">
    <h5 class="mt-0">{{video.snippet.title}}</h5>
    <p class="mt-0">{{video.snippet.description}}</p>
    <h6 class="title">Published By: {{video.snippet.channelTitle}}</h6><br>
    <span>{{video.snippet.publishTime}}</span>
  </div>
</div>
    
</li>

</template>

<script>

export default{

    name:"VideoItem",
    props:{
        video:Object
    },
    computed:{
      thumbNail(){
          return this.video.snippet.thumbnails.default.url
      }  
    }
}


</script>


<style scoped>

.title {
    margin:-10px 0px;
}

.item:hover {

    background-color:gainsboro;
    cursor:pointer;
}

</style>

