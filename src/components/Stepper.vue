<template>
  <div class="stepper-panel">
    <div class="stepper-container d-flex w-100">
      <div
        :class="{ active: stepOneIsActive, checked: stepOneIsChecked }"
        class="step d-flex justify-content-start"
      >
        <div
          class="circle d-flex align-items-center justify-content-center"
        ></div>
        <div class="d-flex align-items-center">寄送地址</div>
        <span class="stepper-line stepper-line-left"></span>
      </div>

      <div
        :class="{ active: stepTwoIsActive, checked: stepTwoIsChecked }"
        class="step d-flex justify-content-center"
      >
        <div
          class="circle d-flex align-items-center justify-content-center"
        ></div>
        <div class="d-flex align-items-center">運送方式</div>
      </div>

      <div
        :class="{ active: stepThreeIsActive, checked: stepThreeIsChecked }"
        class="step d-flex justify-content-end"
      >
        <div
          class="circle d-flex align-items-center justify-content-center"
        ></div>
        <div class="d-flex align-items-center">付款資訊</div> 
        <span class="stepper-line stepper-line-right"></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    initialStep: {
      type: Number,
    }
  },
  data() {
    return {
      stepOneIsActive: false,
      stepOneIsChecked: false,
      stepTwoIsActive: false,
      stepTwoIsChecked: false,
      stepThreeIsActive: false,
      stepThreeIsChecked: false,
    }
  },
  watch: {
    initialStep: {
      handler: function(){
        if (this.initialStep === 0) {
          this.stepOneIsActive = true
          this.stepOneIsChecked = false
          this.stepTwoIsActive = false
          this.stepTwoIsChecked = false
          this.stepThreeIsActive = false
          this.stepThreeIsChecked = false
        } else if (this.initialStep === 1) {
          this.stepOneIsActive = true
          this.stepOneIsChecked = true
          this.stepTwoIsActive = true
          this.stepTwoIsChecked = false
          this.stepThreeIsActive = false
          this.stepThreeIsChecked = false
        } else if (this.initialStep === 2) {
          this.stepOneIsActive = true
          this.stepOneIsChecked = true
          this.stepTwoIsActive = true
          this.stepTwoIsChecked = true
          this.stepThreeIsActive = true
          this.stepThreeIsChecked = false
        }
      }
    }
  }
}
</script>

<style lang="scss">
@mixin getStepNums($num) {
  @for $i from 1 through $num {
    &:nth-child(#{$i}) .circle::after {
      content: "#{$i}";
    }
  }
}
.stepper-panel {
  margin: 24px auto;
}
.step {
  text-align: center;
  @include getStepNums(3);
  width: calc(100% / 3);
  position: relative;
  &.checked,
  &.active {
    .circle {
      background-color: black;
      color: white;
    }
    .stepper-line {
      background-color: black;
    }
  }
  &.checked .circle::after {
    content: "\2714";
  }
}

.circle {
  height: 24px;
  width: 24px;
  margin: 0 8px;
  background-color: white;
  border: solid 1px #afb1bd;
  border-radius: 50%;
  color: #afb1bd;
}

.stepper-line {
  width: 60px;
  height: 1px;
  background-color: #afb1bd;
  // 步驟之間的連結線
  &-right {
    position: absolute;
    top: 50%;
    transform: translateX(-210%);
  }
  &-left {
    position: absolute;
    top: 50%;
    transform: translateX(215%);
  }
}
</style>