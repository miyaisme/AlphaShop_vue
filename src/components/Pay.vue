<template>
  <form id="pay-form" class="form">
              <div class="part m-4">
                <h4 class="title">付款資訊</h4>
                <div class="form-row d-flex flex-wrap">
                  <div class="owner d-flex flex-wrap">
                    <label class="w-100 row-name" for="">持卡人姓名</label>
                    <input type="text" placeholder="請輸入姓名" class="w-100 row-input">
                  </div>
                  <div class="card-number d-flex flex-wrap">
                    <label class="w-100 row-name" for="">卡號</label>
                    <input type="text" placeholder="0000 0000 0000 0000" class="w-100 row-input">
                  </div>
                  <div class="limit w-50 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">有效期限</label>
                    <input type="text" placeholder="MM/YY" class="w-100 mr-8 row-input">
                  </div>
                  <div class="safty-numer w-50 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">CVC/CCV</label>
                    <input type="text" placeholder="000" class="w-100 row-input">
                  </div>
                </div>
              </div>
            </form>
</template>

<style>
.owner, .card-number {
  width: 65%;
}
  .owner, .card-number, .limit, .safty-number {
  margin: 12px 0;
}
.limit {
  padding-right: 15px;
}
</style>