<template>
  <form id="shipping-form" class="form">
    <div class="part m-4">
      <h2>運送方式</h2>
      <div class="deliver-form form-row d-flex flex-wrap">
        <div
          v-for="shippingWay in shippingWays"
          :key="shippingWay.id"
          class="deliver-way row-normal d-flex w-100 my-4"
        >
          <input
            type="radio"
            :id="shippingWay.inputId"
            v-model="selectedFee"
            :value="shippingWay.fee"
            class="shipping-price"
            name="deliver-way"
          />
          <label :for="shippingWay.inputId">
            {{ shippingWay.deliverWay }}
            {{ shippingWay.time }}
            {{ shippingWay.fee | isNumber }}
          </label>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
const dummyData = {
  shippingWays: [
    {
      id: 1,
      inputId: "normal",
      deliverWay: "標準運送",
      time: "約 3~7 個工作天",
      fee: "免費",
    },
    {
      id: 2,
      inputId: "dhl",
      deliverWay: "DHL 貨運",
      time: "48 小時內送達",
      fee: 500,
    },
  ],
};
export default {
  data() {
    return {
      shippingWays: [],
      selectedFee: "",
    };
  },
  created() {
    this.fetchData();
    console.log(this.selectedFee);
  },
  methods: {
    fetchData() {
      this.shippingWays = dummyData.shippingWays;
    },
  },
  filters: {
    isNumber(data) {
      if (typeof data === "number") {
        return `$ ${data}`;
      } else return data;
    },
  },
  watch: {
    selectedFee: {
      handler: function(){
        this.$emit("selected-fee", this.selectedFee)
      }
    }
  }
};
</script>

<style lang="scss">
.deliver-way {
  border: solid 1px #f0f0f5;
  border-radius: 5px;
}
</style>