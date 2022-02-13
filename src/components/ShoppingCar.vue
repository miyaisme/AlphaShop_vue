<template>
<div class="basket-panel m-4">
  <h5 class="title-cart">購物籃</h5>
  <div class="product-container m-4">
       <div 
       v-for="product in products"
       :key="product.id"
       class="product-panel mb-4">
              <div class="image-container">
                <img class="product-image" :src="product.image" alt="#">
              </div>
              <div class="product-content">
                <div class="product-info">
                  <div class="product-name">{{product.name}}</div>
                </div>
                <div class="product-amount">
                  <div data-id="1" 
                  @click="minusAmount(product)"
                  class="minus"></div>
                  <p data-id="1" 
                  v-model="product.amount"
                  class="amount">{{product.amount}}</p>
                  <div data-id="1" 
                  @click="plusAmount(product)"
                  class="plus"></div>
                </div>
                <div class="product-price">
                  <div data-id="1" 
                  v-model="product.prices"
                  class="price">${{product.prices}}</div>
                </div>
              </div>
            </div>
  </div>
  <span class="bottom-line my-center"></span>
  <div class="total-container">
            <div class="fee m-4">
              <div class="deliver-fee">運費</div>
              <div class="cost">免費</div>
            </div>
            <span class="bottom-line my-center"></span>
            <div class="total m-4">
              <div class="total-price">小計</div>
              <div class="final-price"><br>
              $ {{calcTotal}}<br>      
              </div>
            </div>
  </div>
</div>
</template>

<script>
const dummyProduct = {
  products: [
  {
    id: 1,
    name: "破壞補釘修身牛仔褲",
    image: "https://i.imgur.com/L0AOdkW.png",
    amount: 1,
    price: 3999,
    prices: 3999,
  },
  {
    id: 2,
    name: "刷色直筒牛仔褲",
    image: "https://i.imgur.com/VHyllfp.png",
    amount: 1,
    price: 1299,
    prices: 1299,
  }
  ]
}
export default {
  props: {
    deliverFee: {
      type: [Number,String],
    }
  },
  data(){
    return {
      products: [],
    }
  },
  created() {
    this.fetchProduct()
  },
  methods: {
    fetchProduct(){
      const {
        products,
      } = dummyProduct
      this.products = products
    },
    plusAmount(product){
      product.amount += 1
      product.prices = product.price * product.amount
    },
    minusAmount(product){
      if(product.amount <= 1) {
        product.amount = 1
      } else {
        product.amount -= 1
      }
      product.prices = product.price * product.amount
    },
  },
  watch: {
    deliverFee: {
      handler: function(product){
        if(typeof this.deliverFee === "string") {
          this.deliverFee = 0
        }
      }
    },
  },
  computed: {
    calcTotal(){
      let totalPrices = 0
      this.products.forEach(product => {
      totalPrices += product.prices})
      totalPrices += this.deliverFee
      return totalPrices
    }
  }
}
</script>

<style lang="scss">
.title-cart {
  font-weight: 700;
  margin: 16px 30px;
}
  .basket-panel {
  border: solid 1px #f0f0f5;
  border-radius: 8px;
}

.product-image {
  height: 100px;
  width: 100px;
}

.product-name {
  font-size: 1rem;
}

.product-panel {
  display: flex;
  justify-content: space-between;
}

.product-content {
  display: flex;
  flex-flow: column;
  flex-wrap: wrap;
  align-items: flex-start;
  justify-content: space-between;
  align-content: space-between;
  width: 100%;
  height: 70px;
  margin: 0 20px;
}

.product-amount {
  display: flex;
  width: 90px;
  height: 26px;
  justify-content: space-around;
  align-items: center;
}

.minus,
.plus {
  width: 26px;
  height: 26px;
  background-color: #f0f0f5;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.minus::after {
  content: "-";
  font-weight: 1000;
}

.plus::after {
  content: "+";
  font-weight: 1000;
}

.price {
  font-weight: 700;
}

.bottom-line {
  margin: 0 auto;
  display: block;
  width: 90%;
  border: solid 1px #f0f0f5;
  background-color: #f0f0f5;
}

.total-container {
  font-size: 1rem;
}

.cost {
  font-weight: 700;
}

.fee,
.total {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.final-price {
  font-weight: 700;
}

</style>