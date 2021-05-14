<template>
<div class="searchdiv">
<input type="text" placeholder="Write the name of your video  ...." v-model="searchValue" class="inputitem"/>
<button @click="inputfield" class="btn">Search</button>

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
    if(this.searchValue===""){
        alert("please enter a valid search term");
    } else {
    this.$emit("inputChange",this.searchValue);
    this.searchValue="";
    }
}   
}
};

</script>
 

<style scoped>

.searchdiv {
    width: 70%;
    margin:2% auto;
    text-align: center;
}

.inputitem {
    width: 100%;
    height: 35px;
    border-radius: 5px;
    border:1px solid gainsboro;
    text-align: center;
}
.btn {
    background-color: deepskyblue;
    color:white;
    width: 40%;
    margin:2% auto;
    padding: 5px;
    border-radius: 5px;
    border:1px solid gainsboro;
}

</style>