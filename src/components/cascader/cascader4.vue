<template>
    <div id="cascader4">
        <h2> {{menu.name}} </h2>
        <div id="container">
            <div id="parentContainer">
                <div>
                    <ul>
                       <!-- <li v-for=" (link,index) "> -->
                        <!-- </li>  -->
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:"cascader4",
    props:{menu:Object},
    data(){
       return {
           child:Object,
           submenu:Array
       } 
    },methods:{
    // findChildren(item,index){
    // }
    },created:{

    }
}
</script>
<style>
#container{
    display: block;
}
#parentContainer{
    display: flex;
    direction: columns ;
}
</style>
