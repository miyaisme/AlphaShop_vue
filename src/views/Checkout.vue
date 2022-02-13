<template>
  <div class="row checkout container">
    <h2 class="col-12 title">結帳</h2>
      <div class="col">
        <Stepper :initialStep="step" />
        <Address v-show="isAddress" />
        <Shipping v-show="isShipping"
        @selected-fee="addFee" />
        <Pay v-show="isPay" />
        <span class="bottom-line"></span>
        <StepBtn :initialStep="step" @changed-step="refreshStep" />
      </div>
      <div class="col">
        <ShoppingCar :deliverFee="deliverFee" />
      </div>
  </div>
</template>

<script>
import Stepper from "../components/Stepper.vue";
import Address from "../components/Address.vue";
import Shipping from "../components/Shipping.vue";
import Pay from "../components/Pay.vue";
import StepBtn from "../components/StepBtn.vue";
import ShoppingCar from "../components/ShoppingCar.vue";

export default {
  components: {
    Stepper,
    Address,
    Shipping,
    Pay,
    StepBtn,
    ShoppingCar,
  },
  data() {
    return {
      step: -1,
      isAddress: true,
      isShipping: false,
      isPay: false,
      deliverFee: 0 || '',
    };
  },
  created() {
    this.step = 0;
  },
  methods: {
    refreshStep(changedStep) {
      this.step = changedStep;
    },
    addFee(fee){
      this.deliverFee = fee
    },
  },
  watch: {
    step: {
      handler: function () {
        if (this.step === 0) {
          this.isAddress = true;
          this.isShipping = false;
          this.isPay = false;
        } else if (this.step === 1) {
          this.isAddress = false;
          this.isShipping = true;
          this.isPay = false;
        } else if (this.step === 2) {
          this.isAddress = false;
          this.isShipping = false;
          this.isPay = true;
        }
      },
    },
  },
};
</script>

<style>
.checkout {
  margin: 0 auto;
}
.bottom-line {
  margin: 0 auto;
  display: block;
  width: 90%;
  border: solid 1px #f0f0f5;
  background-color: #f0f0f5;
}
</style>