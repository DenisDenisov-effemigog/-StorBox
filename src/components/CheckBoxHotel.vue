<template>
    <div class="checkbox-block checkbox-block-hotel" :editMode="editMode" v-if="editMode==false">
      <h3 class="checkbox-block-hotel-title">Отели</h3>
      <ul class="checkbox-block-list">
       <li v-for="item in 5" :key="item.digit" class=" checkbox-block-hotel-item">
        <a href="#" class="checkbox-block-hotel-link">
            <span>
                {{item}}
            </span>
            <img class="checkbox-block-hotel-img" src="../../public/imgs/star.png" alt="">
            <div class="background"></div>
        </a>
       </li>
      </ul>
     </div>
     <div class="checkbox-block checkbox-block-hotel" v-else>
      <h3 class="checkbox-block-hotel-title">Отели</h3>
      <ul class="checkbox-block-list">
       <li v-for="item in 5" :key="item.digit" class=" checkbox-block-hotel-item checkbox-block-hotel-edit-item" @click="clickEl">
        <a href="#" class="checkbox-block-hotel-link checkbox-block-hotel-edit-link">
            <span>
                {{item}}
            </span>
            <img class="checkbox-block-hotel-img" src="../../public/imgs/star.png" alt="">
            <div  class="background" ></div>
        </a>
       </li>
      </ul>
     </div>
</template>

<script>
export default {
name:"CheckBoxHotel",
props:{
    editMode:{
        type:Boolean,
        required:true
    }
},
methods:{
    clickEl(e){
        e.target.classList.toggle('active')
    }
}
}
</script>

<style scoped>
.checkbox-block-list {
    padding-top: 10px;
 display: flex;
}
.checkbox-block-hotel-img{
    width: 20px;
    height: 20px;
}
.checkbox-block-hotel-link{
    display: flex;
    height: 25px;
    cursor: auto;
}
.checkbox-block-hotel-edit-link{
    cursor: pointer;
}
.checkbox-block-hotel-item{
    border: 1px solid #6e7982;
    margin-right: 10px;
    border-radius: 4px;
    position: relative;
}

.background{
    opacity: 0.5;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: #67727a;
}
.active{
    background: transparent;
}
.checkbox-block-hotel-edit-item:hover .background{
    opacity: 0;
}
span{
    align-self: flex-end;
}
</style>