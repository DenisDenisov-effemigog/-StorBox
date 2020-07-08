<template>
<div  v-if="editMode==false" class="form-row-container">
    <div class="search-preferences">
     <h3 class="search-preferences-title">Поисковые предпочтения</h3>
     <a class="search-preferences-button" @click="editMode = true">
         <SvgIcon name="pencil" />
     </a>
    </div>
    <div class="form-checkbox-block">
        <CheckBoxHotel
            :editMode="editMode"
        />
        <CheckBoxClass 
            :editMode="editMode"
        />
        <CheckBoxTransport
        :editMode="editMode"
        />

    </div>
</div>
<div  v-else class="form-row-container">
    <div class="search-preferences" >
     <h3 class="search-preferences-title">Настройка поисковых предпочтений</h3>
     <a class="search-preferences-button" @click="editMode = false">
         <SvgIcon name="save" />
     </a>
    </div>
    <div class="form-checkbox-block">
        <CheckBoxHotel
            :editMode="editMode"
        />
        <CheckBoxClass
        :editMode="editMode"
        />
        <CheckBoxTransport
        :editMode="editMode"
        />
    </div>
</div>
</template>

<script>
import CheckBoxHotel from "./CheckBoxHotel.vue";
import CheckBoxClass from "./CheckBoxClass.vue";
import CheckBoxTransport from "./CheckBoxTransport.vue";
import SvgIcon from "./SvgIcon.vue";

export default {
    name:"CheckBoxBlock",
    data(){
        return{
            editMode:false
        }
    },
    components:{
        CheckBoxClass,
        CheckBoxHotel,
        SvgIcon,
        CheckBoxTransport,
    }
}
</script>

<style scoped>
    .form-checkbox-block, .search-preferences{
        display: flex;
        justify-content: space-between;
    }
    .form-row-container{
        background-color: #717e88;
        padding-top: 15px;
    }
</style>