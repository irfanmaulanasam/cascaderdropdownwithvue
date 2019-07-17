<template>    
<ul class="sidebar-items">
      <li v-for="(item,index) in items" @click="collapseItem(index, item)" class="item" :key="index"> 
        <router-link :to="item.path">
          <img :src="item.icon" id="item-icon">
          <p aria-readonly="true" class="item-name">{{item.text}}</p>

          <transition name="slide-fade">
            <ul class="child-items" v-if="openedItems[index]">
              <li class="child-item" v-for="(child,index) in item.children" :key="index">
                <router-link :to="child.path" @click.stop>
                  {{child.text}}
                </router-link>
              </li>
            </ul>
          </transition>
        </router-link>
      </li>
    </ul>
</template>
<script>
export default {
    name:"dropdownblack",
    props:{
        model:Object
        },
  data() {
    return {
      openedItems: {},
      selectedSub: '',
      userMenu: false,
      items: [{
          icon: './src/assets/img/icons/dashboard.svg',
          text: 'Element 1',
          path: '#1'
        },
        {
          icon: './src/assets/img/icons/orders.svg',
          text: 'Element 2 with nested',
          path: '',
          children: [{
              icon: 'now-ui-icons files_paper',
              text: 'Nested 1 ',
              path: '/products'
            },
            {
              icon: 'now-ui-icons files_paper',
              text: 'Nested 2',
              path: '/categories'
            },
            {
              icon: 'now-ui-icons location_bookmark',
              text: 'Nested 3',
              path: '/attribute-sets'
            },
            {
              icon: 'now-ui-icons files_box',
              text: 'Nested 4',
              path: '/variant-groups'
            },
            {
              icon: 'now-ui-icons shopping_box',
              text: 'Nested 5',
              path: '/vendors'
            },
            {
              icon: 'now-ui-icons business_chart-bar-32',
              text: 'Nested 6',
              path: '/vat-rates',
              children: [{
                    icon: 'now-ui-icons files_paper',
                    text: 'Nested 1 ',
                    path: '/products'
                    },
                    {
                    icon: 'now-ui-icons files_paper',
                    text: 'Nested 2',
                    path: '/categories'
                    },
                    {
                    icon: 'now-ui-icons location_bookmark',
                    text: 'Nested 3',
                    path: '/attribute-sets'
                    },
                    {
                    icon: 'now-ui-icons files_box',
                    text: 'Nested 4',
                    path: '/variant-groups'
                    },
                    {
                    icon: 'now-ui-icons shopping_box',
                    text: 'Nested 5',
                    path: '/vendors'
                    },
                    {
                    icon: 'now-ui-icons business_chart-bar-32',
                    text: 'Nested 6',
                    path: '/vat-rates'
                    },
                ],
            },
          ],
        },
        {
          icon: './src/assets/img/icons/products.svg',
          text: 'NestedElement',
          path: '',
          children: [{
              icon: 'now-ui-icons files_paper',
              text: 'Nested 1 ',
              path: '/products'
            },
            {
              icon: 'now-ui-icons files_paper',
              text: 'Nested 2',
              path: '/categories'
            },
            {
              icon: 'now-ui-icons location_bookmark',
              text: 'Nested 3',
              path: '/attribute-sets'
            },
            {
              icon: 'now-ui-icons files_box',
              text: 'Nested 4',
              path: '/variant-groups'
            },
            {
              icon: 'now-ui-icons shopping_box',
              text: 'Nested 5',
              path: '/vendors'
            },
            {
              icon: 'now-ui-icons business_chart-bar-32',
              text: 'Nested 6',
              path: '/vat-rates'
            },
          ],
        },
        {
          icon: './src/assets/img/icons/clients.svg',
          text: 'Element 4',
          path: '#3'
        },
        {
          icon: './src/assets/img/icons/marketing.svg',
          text: 'Element 5',
          path: '#4'
        },
        {
          icon: './src/assets/img/icons/reports.svg',
          text: 'Element 6',
          path: '#5'
        },
        {
          icon: './src/assets/img/icons/settings.svg',
          text: 'Element 7',
          path: '#6'
        },
        {
          icon: './src/assets/img/icons/integrations.svg',
          text: 'Element 8',
          path: '#7'
        },

      ],
    }

  },

  methods: {
    collapseItem(index, item) {

      if (item.children != null) {
        this.openedItems[index] = !this.openedItems[index]
        this.$forceUpdate()
      }

    }
  }
}
</script>

<style scoped>
body {
  background-color: #F6F7FB;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}

a {
  color: white;
  text-decoration: none;
}

ul li {
  list-style-type: none;
}

#sidebar {
  background: linear-gradient(#2595ec, #64DD17);
  top: 0;
  left: 0;
  width: 275px;
  height: 1000px;
  position: absolute;
  z-index: -1;
  color: #FFFFFF;
  font-size: 14px;
  display: grid;
  grid-template-columns: 45px 155px 30px 45px;
  grid-template-areas: ". items . ";
  font-weight: bold;
}

.sidebar-items {
  padding-top: 100px;
  grid-area: items;
  margin-left: -40px;
  display: flex;
  flex-direction: column;
}

.item {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  padding-bottom: 10px;
}

#item-icon {
  width: 25px;
  height: auto;
  filter: invert(100%);
  padding-top: 9px;
  padding-right: 15px;
  grid-area: item-icon;
  float: left;
}

.item-name {
  grid-area: item-name;
  position: static;
  float: left;
}

.child-items {
  padding-top: 50px;
  font-size: 12px;
}

.child-item {
  padding-bottom: 15px;
  white-space: nowrap
}

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

</style>
