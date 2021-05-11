<template>
<div>
<input type="text" placeholder="search your video" @input="inputfield" class="inputitem"/>

</div>
</template>


<script>

export default {
name: "SearchBar",

methods:{

inputfield(e){
    this.$emit("inputChange",e.target.value);
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