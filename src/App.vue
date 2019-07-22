<template>
  <div id="app">
    <!-- <div id="container">
      <cascader4/>
      <div id="coresidebar">
        <treemenu 
        :label="datamenu.label" 
        :children="datamenu.children"
        :depth="0"
        />
      </div>
      <div class="corenavbar">
        <cascader
        :menu="navbarmenu"
        />
      </div>
    </div>
    <div>
      <cascader3
      :menu="navbarmenu" 
      />
    </div>  -->
    <!-- <div class="container">
      <cascader4 :menu="navbarmenu" />
    </div> -->
    <div id="container">
    <!-- <carousel1/> -->
    <!-- <carousel2/> -->
    <!-- <carousel3/> -->
    <!-- <carousel4/> -->
    <carousel5/>
    </div>
  </div>
</template>

<script>
// import datamenu from './assets/menu.json'
// import navbarmenu from './assets/menu2.json'
// import treemenu from './components/tree'
// import cascader from './components/cascader2'
// import cascader3 from './components/cascader3'
// import cascader4 from './components/cascader4'
import carousel1 from './components/carousel/carousel1'
import carousel2 from './components/carousel/carousel2'
import carousel3 from './components/carousel/carousel3'
import carousel4 from './components/carousel/carousel4'
import carousel5 from './components/carousel/carousel5'
export default {
  name:'app',
  data: function() {
    return {
      // datamenu,
      // navbarmenu
      }
  },
  components: {
    // treemenu,
    // cascader,
    // cascader3,
    // cascader4
    carousel1,
    carousel2,
    carousel3,
    carousel4,
    carousel5,
  },
};
</script>

<style>
#container {
  display: absolute;

}
#coresidebar{
  background-color: aquamarine;
  outline: 1px #2c3e50;
  width: 20%;
}
#corenavbar{
  background-color: aliceblue;
  border: 50px solid #2c3e50;
  outline: 1px #2c3e50;
}
</style>
