<template>
  <div class="pb-1" :style="{ backgroundImage: `url(${imgUrl.lightPaperFibers})` }">
    <header class="d-flex flex-column align-items-center pt-3">
      <img
        class="img-fluid header-banner-sm"
        src="https://i.im.ge/2023/04/08/IVhAZ4.AnyConv-com-banner-service-sm.webp"
        alt="四隻不同顏色的貓咪頭上有毛孩似繪顏的文字"
        width="348"
        height="215"
      />
      <img
        class="img-fluid header-banner"
        src="https://i.im.ge/2023/04/01/I5ZU1P.banner.webp"
        alt="四隻不同顏色的貓咪中間有毛孩似繪顏的文字"
        width="1440"
        height="288"
      />
    </header>
    <div class="container w-md-60 w-100">
      <form
        class="bg-white shadow p-4 my-5 rounded-4 border-5 border-md-4 border-top border-primary needs-validation"
        novalidate
      >
        <h2 class="fw-bold fs-4 mt-4 mb-5 text-center">填寫訂購資訊</h2>
        <div class="row g-3 mb-3">
          <div class="col-md-6">
            <label for="firstName" class="form-label">名字</label>
            <input type="text" class="form-control" id="firstName" required />
          </div>
          <div class="col-md-6">
            <label for="lastName" class="form-label">姓氏</label>
            <input type="text" class="form-control" id="lastName" required />
          </div>
        </div>
        <div class="col-12 mb-3">
          <label for="phoneNumber" class="form-label">手機號碼</label>
          <input type="tel" class="form-control" id="phoneNumber" required />
        </div>
        <div class="col-12 mb-3">
          <label for="email" class="form-label">電子郵件</label>
          <input type="email" class="form-control" id="email" required />
        </div>
        <div class="col-12 mb-3">
          <label for="address" class="form-label">收件地址</label>
          <div class="row g-3">
            <div class="col-md-6">
              <select class="form-select mb-2">
                <option value="" selected disabled>請選擇城市</option>
                <option value="city1">台北市</option>
                <option value="city2">新北市</option>
                <option value="city3">台中市</option>
                <option value="city4">新竹市</option>
                <option value="city5">彰化市</option>
                <option value="city6">南投市</option>
                <option value="city7">台南市</option>
                <option value="city8">花蓮市</option>
              </select>
            </div>
            <div class="col-md-6">
              <select class="form-select mb-2">
                <option value="" selected disabled>請選擇區域</option>
                <option value="area1">北部區域</option>
                <option value="area2">中部區域</option>
                <option value="area3">南部區域</option>
                <option value="area4">中部區域</option>
                <option value="area5">東部區域</option>
                <option value="area6">外島區域</option>
              </select>
            </div>
          </div>
          <input
            type="text"
            class="form-control"
            id="address"
            placeholder="請輸入詳細地址"
            required
          />
        </div>
        <div class="col-12 mb-3">
          <label for="designer" class="form-label">選擇設計師風格</label>
          <select class="form-select mb-2" id="designer">
            <option value="designer01" selected>Meili</option>
            <option value="designer02">Zoe</option>
            <option value="designer03">Michael</option>
            <option value="designer04">Birdy</option>
          </select>
        </div>
        <div class="col-12 mb-3">
          <label for="payment" class="form-label">付款方式</label>
          <select class="form-select mb-2" id="payment">
            <option value="payment01" selected>貨到付款</option>
            <option value="payment02">信用卡付款</option>
            <option value="payment03">LinePay</option>
            <option value="payment04">街口支付</option>
          </select>
        </div>
        <div class="col-12 mb-3">
          <label for="addOn" class="form-label">加購服務</label>
          <div>
            <div class="form-check form-check-inline">
              <input
                class="form-check-input"
                type="checkbox"
                id="inlineCheckbox1"
                value="addOn01"
              />
              <label class="form-check-label" for="inlineCheckbox1">送禮用包裝+100</label>
            </div>
            <div class="form-check form-check-inline">
              <input
                class="form-check-input"
                type="checkbox"
                id="inlineCheckbox2"
                value="addOn02"
              />
              <label class="form-check-label" for="inlineCheckbox2">無框畫+250</label>
            </div>
          </div>
        </div>
        <div class="col-12 mb-5">
          <label for="comments" class="form-label">備註說明</label>
          <textarea class="form-control" id="comments" rows="5"></textarea>
        </div>
        <div class="text-center mb-4">
          <h3 class="fw-bold fs-4 mb-4">總金額 NT$ 300</h3>
          <button type="submit" class="btn btn-primary rounded-pill fs-4 px-5 fs-5">
            送出訂購資訊
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      imgUrl: {
        lightPaperFibers: 'https://i.im.ge/2023/04/01/I5ZAwx.lightpaperfibers.webp'
      }
    }
  },
  mounted() {
    // 驗證表單
    const forms = document.querySelectorAll('.needs-validation')

    Array.from(forms).forEach((form) => {
      form.addEventListener(
        'submit',
        (event) => {
          if (!form.checkValidity()) {
            event.preventDefault()
            event.stopPropagation()
          }

          form.classList.add('was-validated')
        },
        false
      )
    })
  }
}
</script>
<style lang="scss">
.header-banner-sm {
  display: block;
}

.header-banner {
  display: none;
}

.service-img {
  width: 100px;
  height: 98px;
}

@include media-breakpoint-up(md) {
  .header-banner {
    display: block;
  }
  .header-banner-sm {
    display: none;
  }
  .service-img {
    width: 200px;
    height: 203px;
  }
}
</style>
