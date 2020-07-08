<template>
 <div class="label-container" v-if="editMode==false">
   <a class="form-button" @click="editMode = true">
    <SvgIcon name="pencil" />
    {{title}}
   </a>
 </div>

 <div class="label-container" v-else>
  <label for class="form-label">
   <input :type="inputType" class="form-input"  placeholder="Старый пароль"/> 
   <input :type="inputType" class="form-input"  placeholder="Новый пароль"/> 
   <input :type="inputType" class="form-input" placeholder="Повторите новый пароль"/> 
   <a class="close-btn" @click="editMode = false">X</a>
   <a class="form-button" @click="editMode = false">
    <SvgIcon name="save" />
   </a>
  </label>
 </div>
</template>

<script>
// import Input from './Input.vue'
import SvgIcon from "./SvgIcon.vue";

export default {
 name: "Label",
 components: {
  SvgIcon
  // Input,
 },
 data() {
  return {
   editMode: false
  };
 },
 props: {
  title: {
   type: String,
   required: true
  },
  inputType: {
   type: String,
   required: true
  }
 }
};
</script>

<style scoped>
.form-label{
    display: flex;
    justify-content: space-around;
    width: 100%;
}
.form-input{
    width: 30%;
}
.label-container{
    padding: 10px 0;
}
.close-btn{
    color: red;
    border: 1px solid red;
    border-radius: 50%;
    height: 25px;
    width: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}
</style>