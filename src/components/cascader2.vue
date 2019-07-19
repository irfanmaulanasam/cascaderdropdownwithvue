 <template>
   <div class="navbar">
    <ul id="navmenu">
    <h1> {{menu.label}} </h1>
      <li v-for="(item, index) in menu.children" :key="index">
         <a href="" > {{item.label}} </a>
         <ul class="sub1">
              <li v-for="(link,index) in item.children" :key="index" >
                    <a href=""> {{link.label}} </a>
                    <ul class="sub2">
                      <li v-for=" (link,index) in link.children " :key="index">
                        <a href="">{{link.label}}</a>
                        <ul class="sub3">
                          <li v-for=" (link,index) in link.children " :key="index">
                            <a href="">{{link.label}}</a>
                            <ul class="sub4">
                              <li v-for=" (link,index) in link.children " :key="index">
                                <a href="">{{link.label}}</a>
                                  <ul class="sub5">
                                    <li v-for=" (link,index) in link.children " :key="index">
                                      <a href="">{{link.label}}</a>
                                      <ul class="sub6">
                                        <li v-for=" (link,index) in link.children " :key="index">
                                          <a href="">{{link.label}}</a>
                                        </li>
                                      </ul>
                                    </li>
                                  </ul>
                              </li>
                            </ul>
                          </li>
                        </ul>
                      </li>
                    </ul>
              </li>
         </ul>
      </li>
    </ul>
</div> 
</template>

<script>
export default {
  name: 'cascader2',
  props: {menu:Object},
  data(){
    return {
      openedItems: {},
      selectedSub: '',
      userMenu: false,}
  },
  methods: {
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
*{
    margin: 0px;
    padding: 0px;
}
body{
    font-family: Verdana,;
    background-color: #ABC;
    padding: 50px;
}
h1{
    text-align: center;
    border-bottom: 2px solid #008;
    margin-bottom: 50px;
}
.navbar{
  background-color: #FF0;
}
/* rules for navigation */
ul{
    list-style-type: none;
}
ul#navmenu li{
    /* outline: 1px solid blueviolet; */
    width: 125px;
    text-align: center;
    position: relative;
    float: left;
    margin-right: 4px;
}

ul#navmenu a {
    text-decoration:  none;
    display: block;
    width: 125px;
    height: 25px;
    line-height: 25px;
    background-color: blanchedalmond;
    border: 1px solid #CCC;
    border-radius: 5px; 
}

/* ul#navmenu .sub1 li{
    outline:1px solid green;
} */

ul#navmenu .sub1 a{
    margin-top: 5px;
}

ul#navmenu .sub2 a{
    margin-left: 8px;
}

ul#navmenu li:hover > a {
    background-color: #aaaaaa; 
}

ul#navmenu li:hover a:hover{
    background-color: #FF0;
}
ul#navmenu ul.sub1{
    display: none;
    position: absolute;
    top:26px;
    left: 0px;
}

ul#navmenu ul.sub2{
    display: none;
    position: absolute;
    top: 0px;
    /* bottom: 0px; */
    left: 121px;
}

ul#navmenu ul.sub3{
    display: none;
    position: absolute;
    top: 0px;
    /* bottom: 0px; */
    left: 121px;
}
ul#navmenu ul.sub4{
    display: none;
    position: absolute;
    top: 0px;
    /* bottom: 0px; */
    left: 121px;
}
ul#navmenu ul.sub5{
    display: none;
    position: absolute;
    top: 0px;
    /* bottom: 0px; */
    left: 121px;
}
ul#navmenu ul.sub6{
    display: none;
    position: absolute;
    top: 0px;
    /* bottom: 0px; */
    left: 121px;
}

ul#navmenu li:hover .sub1{
    display: block;
}
ul#navmenu .sub1 li:hover .sub2{
    display: block;
}
ul#navmenu .sub2 li:hover .sub3{
    display: block;
}
ul#navmenu .sub3 li:hover .sub4{
    display: block;
}
ul#navmenu .sub4 li:hover .sub5{
    display: block;
}
ul#navmenu .sub5 li:hover .sub6{
    display: block;
}


</style>

 
 