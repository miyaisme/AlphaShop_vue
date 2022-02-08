<template>
  <div class="container py-5 w-100">
    <h1>結帳</h1>
    <Stepper/>
    <Address v-show="isAddress"/>
    <Shipping v-show="isShipping"/>
    <Pay v-show="isPay"/>
    <span class="bottom-line"></span>
    <StepBtn :step="step"/>
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