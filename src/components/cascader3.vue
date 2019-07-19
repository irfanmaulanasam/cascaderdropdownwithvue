<template>
  <div id="dropdown">
    <div class="containt">
      <loop 
      :label="menu.label" 
      :children="menu.children"
      :depth="0"
      />
    </div>
  </div>
</template>
<script>
import loop from './loop'
export default {
  name:"cascader3",
  props:["menu"],
  components:{
    loop
  }
}
</script>

<style>
#dropdown{
  display: flexbox;
}
.containt{
  display: inline-flexbox;
  flex-direction: column;
}
</style>

