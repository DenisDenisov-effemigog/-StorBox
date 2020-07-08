<template>
 <div class="label-container" v-if="editMode==false">
   <p class="form-paragraph">{{inputValue}}</p>
   <p class="form-title">{{title}}</p>
   <a class="form-button" @click="editMode = true">
    <SvgIcon name="pencil" />
   </a>
 </div>

 <div class="label-container" v-else>
  <label for class="form-label">
   <input :type="inputType" class="form-input" v-model="inputValue" />
   <p class="form-title">{{title}} пользователя</p>
  </label>
  <a class="form-button" @click="editMode = false">
    <SvgIcon name="save" />
   </a>
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
   editMode: false,
   inputValue:""
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
.label-container{
 background-color: #2a2a3c;
}
.form-label, .label-container {
 height: 45px;
 display: flex;
 align-items: center;
}
.form-label{
  flex: 1;
}
.form-title{
  flex: 1;
}
.form-paragraph {
 width: 170px;
 height: 22px;
 border: 1px solid #fff;
 background-color: transparent;
 margin-right: 15px;
 
}
.form-input{
 margin-right: 15px;
}
</style>