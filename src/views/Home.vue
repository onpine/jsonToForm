<template>
  <div class="home">
    <div class="phone-box">
      <div class="head">灭火器表单</div>
      <Box
        v-for="(item, index) in jsonData"
        :key="item.id"
        :state="{ ...item, index }"
        :selected.sync="selectValue"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Box from "../components/box";
import jsonData from "../utils/form.json";
export default {
  name: "Home",
  components: {
    Box,
  },
  data() {
    return {
      jsonData,
      selectValue: 1,
    };
  },
};
</script>

<style lang="less" scoped>
.home {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  .phone-box {
    width: 375px;
    height: 667px;
    box-sizing: content-box;
    border: 2px solid slateblue;
    border-radius: 20px;
    background-color: #dfdfdf;
    .head {
      height: 50px;
      line-height: 50px;
      background-color: #fff;
      border-radius: 20px 20px 0 0;
    }
  }
}
</style>
