<template>
<div>
<input type="text" placeholder="search your video" v-model="searchValue" class="inputitem"/>
<button @click="inputfield">Search</button>

</div>
</template>


<script>

export default {
name: "SearchBar",

data(){

    return{
        searchValue: ""
    }

},

methods:{

inputfield(){
    this.$emit("inputChange",this.searchValue);
    this.searchValue="";
}   

}
};

</script>
 

<style>

.inputitem {
    width: 100%;
    height: 50px;
}

</style>