<template>
  <div id="app">
      <!-- <ul class="cd-accordion-menu">
        <item :model="model"></item>
      </ul> -->
    <!-- <dropdown :menu="model"/> -->
    <cascader2 :menu="datamenu"/>
  </div>
</template>

<script>
// import dropdown from './components/dropdown.vue'
// import item from './components/cascader3.vue'
import cascader2 from './components/cascader2'
import datamenu from './assets/menu.json'

let model = { name: "init" 
      ,children:[{
        name:'link1',
        children:[
          {name:'sublink1'},
          {name:'sublink2'},
          {name:'sublink3'},
          {name:'sublink4',
            children:[
              {name:'sublink1'},
              {name:'sublink2'},
              {name:'sublink3'},
              ]}
        ]
        },{
        name:'link2',
        children:[
          {name:'sublink1'},
          {name:'sublink2'},
          {name:'sublink3'},
          {name:'sublink4'}
          ]
        },{
        name:'link3'
      }]
  };
export default {
  data: function() {
    return {datamenu,model}
  },
  components: {
    // dropdown,
    // item,
    cascader2
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
