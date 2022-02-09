<template>
  <div class="container py-5 w-100">
    <h1>結帳</h1>
    <Stepper
    :initialStep="step"
    />
    <Address v-show="isAddress"/>
    <Shipping v-show="isShipping"/>
    <Pay v-show="isPay"/>
    <span class="bottom-line"></span>
    <StepBtn 
    :initialStep="step"
    @changed-step="refreshStep"
    />
  </div>
</template>

<script>
import Stepper from '../components/Stepper.vue'
import Address from '../components/Address.vue'
import Shipping from '../components/Shipping.vue'
import Pay from '../components/Pay.vue'
import StepBtn from '../components/StepBtn.vue'

export default {
  components: {
    Stepper,
    Address,
    Shipping,
    Pay,
    StepBtn,
  },
  data() {
    return {
      step: -1,
      isAddress: true,
      isShipping: false,
      isPay: false,
    }
  },
  created() {
    this.step = 0
  },
  methods: {
    refreshStep(changedStep) {
      this.step = changedStep
    }
  },
  watch: {
    step: {
      handler: function(){
        if (this.step === 0) {
          this.isAddress = true
          this.isShipping = false
          this.isPay = false
        } else if (this.step === 1) {
          this.isAddress = false
          this.isShipping = true
          this.isPay = false 
        } else if (this.step === 2) {
          this.isAddress = false
          this.isShipping = false
          this.isPay = true
        }
      }
    }
  }
}
</script>

<style>
.bottom-line {
  display: block;
  width: 90%;
  border: solid 1px #f0f0f5;
  background-color: #f0f0f5;
}
</style>