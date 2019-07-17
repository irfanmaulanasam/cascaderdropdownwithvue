<template>
    <ul>
        <li v-for="(item,index) in submenus" :key="index">
            {{item.name}}
        </li>
    </ul>
</template>

<script>
export default {
    name:"loop",
    props:["submenus"]
}
</script>
