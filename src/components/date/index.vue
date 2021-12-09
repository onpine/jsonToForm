<template>
  <div class="form-date">
    <a-date-picker v-model:value="value1" />
  </div>
</template>

<script>
export default {
  name: "formDate",
  data() {
    return {
      value1: "",
    };
  },
};
</script>

<style></style>
