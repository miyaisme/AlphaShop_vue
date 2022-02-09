<template>
  <div class="stepper-panel">
    <div class="stepper-container d-flex w-100 my-center">
      <div
        :class="{ active: stepOneIsActive, checked: stepOneIsChecked }"
        class="step d-flex justify-content-start"
      >
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
        <span class="stepper-line stepper-line-left"></span>
      </div>

      <div
        :class="{ active: stepTwoIsActive, checked: stepTwoIsChecked }"
        class="step d-flex justify-content-center"
      >
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
      </div>

      <div
        :class="{ active: stepThreeIsActive, checked: stepThreeIsChecked }"
        class="step d-flex justify-content-end"
      >
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
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
  height: 32px;
  width: 32px;
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
    right: calc(0% + 44px);
    transform: translate(-50%, 0%);
  }
  &-left {
    position: absolute;
    top: 50%;
    left: calc(50% + 44px);
    transform: translate(-50%, 50%);
  }
}
</style>