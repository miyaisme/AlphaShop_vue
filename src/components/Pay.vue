<template>
  <form id="pay-form" class="form">
              <div class="part m-4">
                <h2>付款資訊</h2>
                <div class="form-row d-flex flex-wrap">
                  <div class="owner w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">持卡人姓名</label>
                    <input type="text" value="John Doe" class="w-100 row-input">
                  </div>
                  <div class="card-number w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">卡號</label>
                    <input type="text" value="1111 2222 3333 4444" class="w-100 row-input">
                  </div>
                  <div class="limit w-50 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">有效期限</label>
                    <input type="text" value="MM/YY" class="w-100 mr-8 row-input">
                  </div>
                  <div class="safty-numer w-50 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">CVC/CCV</label>
                    <input type="text" value="123" class="w-100 row-input">
                  </div>
                </div>
              </div>
            </form>
</template>