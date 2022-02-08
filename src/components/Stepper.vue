<template>
  <div class="stepper-panel">
    <div class="stepper-container d-flex w-100 my-center">
      <div class="step d-flex justify-content-start">
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
        <span class="stepper-line stepper-line-left"></span>
      </div>

      <div class="step d-flex justify-content-center">
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
      </div>

      <div class="step d-flex justify-content-end">
        <div
          class="circle m-4 d-flex align-items-center justify-content-center"
        ></div>
        <span class="stepper-line stepper-line-right"></span>
      </div>
    </div>
  </div>
</template>

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