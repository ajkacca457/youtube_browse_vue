<template>

<li class="list-group-item my-2 border-1 rounded item media" @click="selectvideo">
  <img :src="thumbNail" alt="Generic placeholder image" >
  <div class="media-body">
    <h6 class="text-secondary">{{video.snippet.title}}</h6>
    </div>
</li>

</template>

<script>

export default{

    name:"VideoItem",
    props:{
        video:Object
    },
    methods:{
        selectvideo(){
            this.$emit("videoselect",this.video)
        }
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

img {
    margin-right:10px;
}
.item {
    display: flex;
}

.item:hover {

    background-color:gainsboro;
    cursor:pointer;
}

</style>

