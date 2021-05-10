<template>
<div>
<input type="text" placeholder="search your video" @input="inputfield"/>
</div>
</template>


<script>

export default {
name: "SearchBar",
methods:{

inputfield(e){
    console.log(e.target.value)
}    

}
};

</script>


<style>

</style>