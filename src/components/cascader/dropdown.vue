<template>
   <div class="dropdown">
  <button class="dropbtn">{{menu.name}}</button>
  <div class="dropdown-content">
    <ul>
      <li v-for="(item, index) in menu.children" :key="index" >
         <a href="" > {{item.name}} </a>
          <ul v-if="item.children">
              <li v-for="(subitem,index) in item.children" :key="index" >
                  <div class="dropdown-subcontent">
                    <a href=""> {{subitem.name}} </a>
                  </div> 
                <ul v-if="subitem.children">
                  <li v-for="(link,index) in subitem.children" :key="index">
                    <a href="">{{link}}</a>
                  </li>
                </ul>
              </li>
          </ul>
      </li>
    </ul>
  </div>
</div> 
</template>

<script>
import loop from './loop.vue'
export default {
  name: 'dropdown',
  props: {menu:Object},
  data(){
    return {
      openedItems: {},
      selectedSub: '',
      userMenu: false,}
  },
  components:{
    loop
  },methods: {
    collapseItems(item,index){
      if (item.children != null) {
        this.openedItems[index] = !this.openedItems[index]
        this.$forceUpdate()
      }
    }
  }
}
</script>

<style scoped>
a {
  display: block;
  width: 100%;
  height: 100%;
  cursor: pointer;
}

ul{
  display: inline-block;
list-style: none;
}
li{
float: left;
}

.dropbtn {
  background-color: rgb(71, 72, 71);
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
}
/* trancition for children */
.slide-fade-enter-active {
  transition: all .8s ease;
}

.slide-fade-leave-active {
  transition: all .3s cubic-bezier(0.5, 1.0, 0.8, 1.0);
}

.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateY(-10px);
  opacity: 0;
}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}
.dropdown-subcontent {
  display: none;
  position: relative;
  background-color: #f1f1f1;
  min-width: 60px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: rgb(164, 161, 161);}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {display: inline-flex;}
.dropdown-content:hover .dropdown-subcontent {display: block;}
/* Change the background color of the dropdown button when the dropdown content is shown */
.dropdown:hover .dropbtn {background-color: #ffffff; color: rgb(32, 31, 31)}
</style>
