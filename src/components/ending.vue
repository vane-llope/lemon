<template>
  <div>
    <div class="container mt-5">
      <hr style="margin:40px 0"/>
      <div class="row">
        <div class="col-md mb-5 contactimg">
          <img
            class="rounded-circle"
            style="width: 60%; margin-left: 50px"
            src="../assets/images/contact.jpg"
            alt=""
          />
        </div>

        <div class="col-md mb-5">
          <div class="container">
          <p style="text-align: end"><strong>راه های ارتباطی</strong></p>
          <p style="text-align: end">
            این
            <span class="web">وبسایت</span>
            با هدف ارائه محاسبات و ابزارهای آنلاین شروع به کار کرده است
            ابزارهایی که هر جایی ممکن است مورد نیاز باشد
            <br>
            شما می توانید برای کمک به ما جهت بهتر شدن امکانات و ابزار های آنلاین
            یا افزودن ابزار های جدید ویا موارد دیگر نظرات، پیشنهادات و انتقادات
            خود را با ما درمیان بگذارید
          </p>
          </div>
          <div class="mt-5 media">
            <a href="#" class="fa fa-instagram"></a>
            <a href="#" class="fa fa-whatsapp"></a>
            <a href="#" class="fa fa-telegram"></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ending",
};
</script>
<style scoped>
.media {
  margin-left: 40%;
}
.media a {
  margin-left: 20px;
}
.fa {
  border-radius: 50%;
  padding: 20px;
  font-size: 30px;
  width: 80px;
  text-align: center;
  text-decoration: none;
  margin: 5px 2px;
}

.fa:hover {
  opacity: 0.7;
}
.fa-instagram {
  background: #cb2027;
  color: white;
}
.fa-whatsapp {
  background: #3cdd1c;
  color: white;
}
.fa-telegram {
  background: #066496;
  color: white;
}
@media(max-width:876px){
  .media{
    margin-left: 0;
  }
}
</style>