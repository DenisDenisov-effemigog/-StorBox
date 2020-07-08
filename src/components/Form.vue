<template>
 <div class="form-block">
  <h2 class="form-block-title">Настройка учетной записи</h2>
  <form action class="form">
   <div class="form-row">
    <InputBlock />
   </div>
   <CheckBoxBlock />
  </form>
 </div>
</template>

<script>
import CheckBoxBlock from "./CheckBoxBlock.vue";
import InputBlock from "./InputBlock.vue";

export default {
 name: "Form",
 components: {
  CheckBoxBlock,
  InputBlock
 },
};
</script>

<style scoped>
.form-block {
 border: 2px solid #000;
 border-radius: 5px;
 padding: 15px;
}
</style>