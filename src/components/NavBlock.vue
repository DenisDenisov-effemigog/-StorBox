<template>
 <nav class="nav-block">
  <ul class="nav-list">
   <li class="nav-item" v-for="item in dataItems" :key="item.name">
    <div class="nav-page">
     <a :href="item.href" class="nav-link">
      <SvgIcon :name ="item.name"/>
     </a>
    </div>
   </li>
  </ul>
 </nav>
</template>

<script>
import SvgIcon from './SvgIcon.vue'

export default {
 name: "NavBlock",
 components:{
     SvgIcon
 },
  data(){
        return{
            dataItems:[
                {name: "user", href: "#"},
                {name: "smart-cart", href: "#"},
                {name: "metal-gear", href: "#"}
            ]
        }
  }
};
</script>

<style scoped>
.nav-block {
 display: flex;
 justify-content: center;
}
.nav-list {
 display: flex;
}
.nav-item {
 padding-right: 10px;
 border-bottom: 1px solid transparent;
 padding-bottom: 5px;
}
.nav-item:hover {
 border-bottom-color: #fff;
}
.nav-item:hover .svg-icon--user {
 fill: #fff;
}

.nav-item:hover .svg-icon--smart-cart {
 fill: #fff;
}

.nav-item:hover .svg-icon--metal-gear{
 fill: #fff;
}

.svg-icon--smart-cart, .svg-icon--user, .svg-icon--metal-gear{
    width: 42px;
    height: 38px;
}
.nav-item:last-child {
 padding-right: 0;
}
.nav-page {
 border: 1px solid #a9a9ab;
 padding: 5px;
 border-radius: 50%;
}
</style>