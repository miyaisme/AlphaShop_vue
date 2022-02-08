<template>
  <div class="form-panel">
          <div class="form-container">
            <form id="address-form" class="form">
              <div class="part m-4">
                <h2>寄送地址</h2>
                <div class="form-row d-flex flex-wrap">
                  <div class="gender w-50 d-flex flex-wrap">
                    <label class="row-name w-100" for="">稱謂</label>
                    <div class="select-wrapper w-100 mr-8">
                      <select name="gender" id="gender" class="w-100 mr-8 row-select">
                        <optgroup>
                          <option value="先生">先生</option>
                          <option value="小姐">小姐</option>
                          <option value="其他">其他</option>
                        </optgroup>
                      </select>
                    </div>
                  </div>
                  <div class="name w-50 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">姓名</label>
                    <input type="text" value="請輸入姓名" class="w-100 row-input">
                  </div>
                  <div class="phone w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">電話</label>
                    <input type="text" value="請輸入行動電話" class="input-phone w-100 row-input">
                  </div>
                  <div class="email w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">Email</label>
                    <input type="text" value="請輸入電子郵件" class="w-100 row-input">
                  </div>
                  <div class="city w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">縣市</label>
                    <div class="select-city select-wrapper w-100">
                      <select name="city" id="city" class="w-100 row-select">
                        <optgroup>
                          <option value="city-select">請選擇縣市</option>
                          <option value="基隆縣">基隆縣</option>
                          <option value="基隆市">基隆市</option>
                          <option value="台北市">台北市</option>
                          <option value="新北市">新北市</option>
                        </optgroup>
                      </select>
                    </div>
                  </div>
                  <div class="adress w-100 d-flex flex-wrap">
                    <label class="w-100 row-name" for="">地址</label>
                    <input type="text" value="請輸入地址" class="w-100 row-input">
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
</template>