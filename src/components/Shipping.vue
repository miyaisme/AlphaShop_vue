<template>
  <form id="shipping-form" class="form">
              <div class="part m-4">
                <h2>運送方式</h2>
                <div class="deliver-form form-row d-flex flex-wrap">
                  <div class="deliver-way row-normal d-flex w-100 my-4">
                    <input type="radio" id="normal-deliver" class="circle-normal">
                    <div class="normal d-flex w-75 justify-content-between align-items-center">
                      <div class="left-normal-deliver d-flex flex-column"><label for="normal-deliver"
                          class="deliver">標準運送</label>
                        <label for="normal-deliver" class="info">約 3~7 個工作天</label>
                      </div>
                      <div class="right-normal-deliver">
                        <label for="normal-deliver" class="shipping-price">免費</label>
                      </div>
                    </div>
                  </div>
                  <div class="deliver-way row-dhl  d-flex w-100 my-4">
                    <input type="radio" id="dhl-deliver" class="circle-dhl">
                    <div class="dhl d-flex w-75 justify-content-between align-items-center">
                      <div class="left-dhl-deliver d-flex flex-column"><label for="dhl-deliver" class="deliver">DHL
                          貨運</label>
                        <label for="dhl-deliver" class="info">48 小時內送達</label>
                      </div>
                      <div class="right-dhl-deliver">
                        <label for="dhl-deliver" class="shipping-price">$500</label>
                      </div>
                    </div>

                  </div>
                </div>
              </div>
            </form>
</template>