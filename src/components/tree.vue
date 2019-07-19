<template>
  <div class="tree-menu">
    <div :style="indent" @mouseover="mouseover" id="loop">{{ label }}</div>
   <slot 
      v-if="showChildren"
   >
    <tree-menu 
      v-for="(node,index) in children" 
      :children="node.children" 
      :label="node.label"
      :depth="depth + 1"
      :key="index"
   />
   </slot>
  </div>
</template>
<script>
  export default { 
    name: 'tree-menu',
    props: [ 'label', 'children', 'depth' ],
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
.tree-menu{
  margin: 5px;
  background-color: beige;
}
#loop{
  outline: 3px dotted slateblue;
  background-color: sandybrown; 
  width: 50px;
}

</style>

