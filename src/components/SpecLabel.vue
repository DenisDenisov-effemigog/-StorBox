<template>
 <div class="label-container" v-if="editMode==false">
  <div class="block">
   <p class="form-paragraph">{{birthday}}</p>
   <p>День рождения</p>
  </div>
  <div class="block">
   <p class="form-paragraph">{{gender}}</p>
   <p>Пол</p>
  </div>
  <a class="form-button" @click="editMode = true">
   <SvgIcon name="pencil" />
  </a>
 </div>
 <div class="label-container" v-else>
  <label for class="form-label">
   <input :type="inputType" class="form-input" v-model="birthday"/>
   День рождения пользователя
  </label>
  <label for class="form-label">
   <input :type="inputType" class="form-input" v-model="gender" />
   Пол пользователя
  </label>
  <a class="form-button" @click="editMode = false">
    <SvgIcon name="save" />
   </a>
 </div>
</template>

<script>
import SvgIcon from "./SvgIcon.vue";

export default {
 name: "SpecLabel",
 components: {
  SvgIcon
  // Input,
 },
 data() {
  return {
   editMode: false,
   gender:'',
birthday:''
  };
 },
 methods:{
   change(event){
     console.log(event.target.value)
   }
 },
 props: {
  title: {
   type: String
  },
  inputType: {
   type: String,
   required: true
  }
 }
};
</script>

<style scoped>
.block{
  display: flex;
  flex: 1;
}
.label-container {
 background-color: #2a2a3c;
}
.form-label,
.label-container {
 height: 45px;
 display: flex;
 align-items: center;
}
.form-paragraph {
 width: 170px;
 height: 22px;
 border: 1px solid #fff;
 background-color: transparent;
 margin-right: 10px;
}
.form-input{
  margin-right: 10px;
}
.form-label{
  flex: 1;
}
</style>