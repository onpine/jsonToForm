<template>
  <div class="form-radio">
    <a-radio-group v-model:value="value">
      <a-radio :value="1">A</a-radio>
      <a-radio :value="2">B</a-radio>
    </a-radio-group>
  </div>
</template>

<script>
export default {
  name: "formRadio",
  data() {
    return {
      value: 1,
    };
  },
};
</script>

<style lang="less" scoped></style>
