<template>
  <div
    :class="['box', selected == state.index ? 'selected' : '']"
    @click="handleSelected"
  >
    <div class="title">
      {{ state.cname }}
      <span class="sub-text" v-if="state.isRequired">*必填项，不能为空</span>
    </div>
    <div class="content">
      <component v-bind:is="componentName"></component>
    </div>
  </div>
</template>

<script>
/**
 * 组件类型与组件文件名称的枚举
 */
const compTypeEnum = {
  3: "radio",
  7: "date",
};

export default {
  name: "box",
  components: {},
  props: {
    state: {
      type: Object,
      require: true,
    },
    selected: {
      type: Number,
    },
  },
  data() {
    return {
      compType: this.state.compType,
      compTypeEnum,
    };
  },
  computed: {
    componentName() {
      return () => import(`../${this.compTypeEnum[this.compType]}`);
    },
  },
  mounted() {},
  methods: {
    handleSelected() {
      console.log(this.state.index);
      this.$emit("update:selected", this.state.index);
    },
  },
};
</script>

<style lang="less" scoped>
.selected {
  border: 2px solid cornflowerblue !important;
}
.box {
  height: 100px;
  width: 100%;
  border-radius: 10px;
  border: 2px solid transparent;
  padding: 0 20px;
  margin: 5px 0;
  cursor: pointer;
  .title {
    height: 40px;
    width: 100%;
    line-height: 40px;
    text-align: left;
    .sub-text {
      color: crimson;
      font-size: 12px;
    }
  }
  .content {
    height: 50px;
    line-height: 50px;
    width: 100%;
    text-align: left;
    margin-bottom: 10px;
  }
}
</style>
