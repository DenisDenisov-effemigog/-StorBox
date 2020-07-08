<template>
    <div class="checkbox-block checkbox-block-transport" :editMode="editMode" v-if="editMode==false">
      <h3 class="checkbox-block-transport-title">Транспорт</h3>
      <ul class="checkbox-block-list">
       <li v-for="item in ['plane','train', 'transport']" :key="item" class=" checkbox-block-transport-item">
        <a href="#" class="checkbox-block-transport-link">
              <SvgIcon class="transport-icon" :name="item" />
        </a>
       </li>
      </ul>
     </div>
     <div class="checkbox-block checkbox-block-transport" v-else>
      <h3 class="checkbox-block-transport-title">Транспорт</h3>
      <ul class="checkbox-block-list">
       <li v-for="item in ['plane','train', 'transport']" :key="item" class=" checkbox-block-transport-item checkbox-block-transport-edit-item">
        <a href="#" class="checkbox-block-transport-link checkbox-block-transport-edit-link" @click="clickEl">
              <SvgIcon class="transport-icon" :name="item" />
        </a>
       </li>
      </ul>
     </div>
</template>

<script>
import SvgIcon from "./SvgIcon.vue";

export default {
name:"CheckBoxTransport",
components:{
    SvgIcon
},
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
.transport-icon{
    width: 25px;
    height: 25px;
}
.checkbox-block-list{
    display: flex;
    padding-top: 10px;
}
.checkbox-block-transport-item{
    width: 30px;
    height: 35px;
    margin-right: 10px;
    border-radius: 4px;
    position: relative;
}
.checkbox-block-transport-edit-item:hover .transport-icon{
    fill: #fcfdfd;
}
.checkbox-block-transport-edit-item:hover{
    border-color: #fcfdfd;
}
.checkbox-block-transport-edit-link , .checkbox-block-transport-link{
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid #67727a;
    background-color: #67727a;
     width: 100%;
    height: 100%;
}
.active{
    fill: #fcfdfd;
    
    
}
</style>