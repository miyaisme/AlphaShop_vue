<template>
  <div
    id="control-panel"
    class="control-panel m-4 d-flex justify-content-between"
  >
    <button @click.stop.prevent="stepMinus()" class="back d-flex align-items-start">← 上一步</button>
    <button @click.stop.prevent="stepPlus()" class="next active">
      → 下一步
    </button>
  </div>
</template>

<script>
export default {
  props: {
    initialStep: {
      type: Number,
    },
  },
  data() {
    return {
      step: this.initialStep,
    };
  },
  created() {
    this.step = 0;
  },
  methods: {
    stepPlus() {
      this.step += 1;
      this.judgeStep;
      const changedStep = this.step;
      this.$emit("changed-step", changedStep);
    },
    stepMinus() {
      this.step -= 1;
      this.judgeStep;
      const changedStep = this.step;
      this.$emit("changed-step", changedStep);
    },
  },
  computed: {
    judgeStep: function () {
      if (this.step <= 0) {
        return (this.step = 0);
      } else if (this.step >= 2) {
        return (this.step = 2);
      }
    },
  },
};
</script>

<style lang="scss">
/* basic setting */
$body-bg: rgb(255, 255, 255);
$body-color: #000000;
$white: #fff;
$black: #000000;
$pink: #f67599;
$gray: #f0f0f5;
.back,
.next,
.first-next {
  width: 156px;
  height: 40px;
  border-radius: 4px;
  background-color: white;
  &.active {
    background-color: $pink;
    color: white;
  }
  &.hidden {
    visibility: hidden;
  }
}
</style>