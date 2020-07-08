<template>
    <div class="checkbox-block checkbox-block-class" :editMode="editMode" v-if="editMode==false">
      <h3 class="checkbox-block-class-title">Класс</h3>
      <ul class="checkbox-block-list">
       <li v-for="item in ['E','B']" :key="item" class=" checkbox-block-class-item">
        <a href="#" class="checkbox-block-class-link">
            <span class="class-span">
                {{item}}
            </span>
            <span>class</span>
        </a>
       </li>
      </ul>
     </div>
     <div class="checkbox-block checkbox-block-class" v-else>
      <h3 class="checkbox-block-class-title">Класс</h3>
      <ul class="checkbox-block-list">
       <li @click="clickEl" v-for="item in ['E','B']" :key="item" class=" checkbox-block-class-item checkbox-block-class-edit-item">
        <a href="#" class="checkbox-block-class-link">
            <span class="class-span">
                {{item}}
            </span>
            <span>class</span>
        </a>
       </li>
      </ul>
     </div>
</template>

<script>
export default {
name:"CheckBoxClass",
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
.checkbox-block-list{
    display: flex;
    padding-top: 10px;
}
.checkbox-block-class-item{
    margin-right: 15px;
    position: relative;
}
.checkbox-block-class-link{
    display: flex;
    flex-direction: column;
}
.checkbox-block-class-img{
    position: absolute;
    top: 20px;
    right: 4px;
}
.class-span{
    font-size: 25px;
    color: #818a92;
    border: 1px solid #818a92;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    text-align: center;
}
.checkbox-block-class-edit-item:hover .class-span{
    color: #fff;
    border-color: #fff;
}
.active{
    color: #fff;
    border-color: #fff;
}

</style>