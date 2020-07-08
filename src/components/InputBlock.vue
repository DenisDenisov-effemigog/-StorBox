<template>
 <div class="form-row">
  <Label title="Логин" inputType="text" />
  <Label title="Имя" inputType="text" />
  <Label title="Фамилия" inputType="text" />
  <PassLabel title="Сменить пароль" inputType="password" />
  <Label title="E-mail" inputType="e-mail" />
  <Label title="Телефон" inputType="text" />
  <SpecLabel inputType="text" />
 </div>
</template>

<script>
import Label from "./Label.vue";
import PassLabel from "./PassLabel.vue";
import SpecLabel from "./SpecLabel.vue";
export default {
 name: "InputBlock",
 components: {
  PassLabel,
  Label,
  SpecLabel
 }
};
</script>

<style scoped>
.form-row {
 display: flex;
 flex-direction: column;
}

.label-container:nth-child(even) {
 background-color: #3e4453;
}
</style>