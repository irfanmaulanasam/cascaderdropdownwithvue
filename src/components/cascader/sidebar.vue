<template>
    <div class="label-wrapper" @click="toggleChildren">
      <div :style="indent" :class="labelClasses">
        <i v-if="nodes" class="fa" :class="iconClasses"></i>
        {{ label }}
      </div>
    </div>
</template>

<script>
export default { 
      name: 'tree-menu',
      props: [ 'nodes', 'label', 'depth' ],
      data() {
         return {
           showChildren: false
         }
      },
      computed: {
        iconClasses() {
          return {
            'fa-plus-square-o': !this.showChildren,
            'fa-minus-square-o': this.showChildren
          }
        },
        labelClasses() {
          return { 'has-children': this.nodes }
        },
        indent() {
          return { transform: `translate(${this.depth * 50}px)` }
        }
      },
      methods: {
        toggleChildren() {
           this.showChildren = !this.showChildren;
        }
      }
}
</script>
