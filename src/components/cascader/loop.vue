<template>
<div id="loop">
    <div :style="indent" @mouseover="mouseover" id="loop">{{ label }}</div>
   <slot 
      v-if="showChildren"
   >
    <loop v-for=" (link,index) in children " 
    :children="link.children" 
    :label="link.label"
    :depth="depth + 1"
    :key="index"
    />
   </slot>
</div>
</template>

<script>
export default {
    name:"loop",
    props:["label","children","depth"],
    data() {
      return { showChildren: false }
    },
    computed: {
      indent() {
        return { transform: `translate(${this.depth * 0}px)` }
      }
    },
    methods: {
      mouseover(){
        this.showChildren = !this.showChildren;
      }
    }
}
</script>

<style>
#loop{
    display: grid;
}
</style>

