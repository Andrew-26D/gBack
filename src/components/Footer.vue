<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import webForm from '../assets/pwaLogo.svg'
import minimalLogo from '../assets/gbackLogoFooter.svg'
 
const hideHeader = ref(false)
let lastScrollY = 0
const handleScroll = () => {
  if (window.scrollY > lastScrollY) {
    hideHeader.value = true
  } else {
    hideHeader.value = false
  }
  lastScrollY = window.scrollY
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
<template>
<footer class="footer">
  <section>
    <img :src="minimalLogo" alt="">
    <article>
      <a href="" class="government"><img src="" alt=""> </a>
      <a href="" class="government"> <img src="" alt=""></a>
    </article>
  </section>


  <section class="footer-links">
<ul>
  <li><a href="https://gback.ir/blog/">بلاگ</a></li>
  <li><a href="https://gback.ir/about" target="blank">درباره ما</a></li>
  <li><a href="https://gback.ir/storedetail" target="blank">فروشگاه ها</a></li>
  <li><a href="https://gback.ir/contact" target="blank">تماس با ما</a></li>
</ul>
  </section>

  <section> <p> پشتیبانی جیبک</p>
  <p>آدرس:
تهران، جردن، عاطفی غربی، پ ٩٠<br>
ساعات کاری:
۹ الی ۱۷</p>
  <a href=""> <img src="http://www.w3.org/1999/xlink" alt=""></a
  ><a href=""><img src="" alt=""></a>
  <a href="https://www.instagram.com/gback.ir/?igsh=dGxwMTRkOW53MDRv#" target="blank"><img src="" alt=""></a>
   </section>


  <section ><a href="https://app.gback.ir/?rf=gback.ir" target="blank"> <button class="footerBtn"> نسحه وب  <img :src="webForm" alt=""> </button></a></section>

</footer>
    
</template>

<style scoped>
html, body {
  scroll-behavior: smooth;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  overflow-x: hidden;
  font-family: 'Yekan', sans-serif;
}
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
a{
    text-decoration: none;
    color: white;
}
.footer{
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 160px;
  width: 100dvw;
  background-color:#2A2A2A;
  font-family: 'Yekan', sans-serif;
  padding: 28px 138px 28px 138px ;
}
.footer p{
  height: 35px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  direction: rtl;
  font-size: 18px;
  color: white;
  line-height: 24px;
  margin-bottom: 8px;
}
.footer-links ul{
  list-style: none;
  display: flex;
  gap: 2px;
  direction: rtl;
flex-direction: column;
  color: white;
  margin: 20px;
  border-radius: 12px;
  list-style: none;
  font-size: 18px;
}
.footerBtn{
  width: 188px;
  height: 52px;
  border-radius: 14px;
  background-color:rgba(255, 255, 255, 0);
  color: white;
  border: #d9856d 1px solid;
  font-family: 'Yekan', sans-serif;
  font-size: 20px;
  cursor: pointer;
  text-align: center;
  transition: all 0.3s ease-in-out;
}
.footerBtn:hover{
  background-color: #8d341a;
  color: white;
  border: none;
  font-family: 'Yekan', sans-serif;
}
.government{
  height: 72px;
  width: 72px;
  margin: 0 0 0 11px;
  background-color: #30281e;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 8px 32px;
  border-radius: 8px;
}
.footer article{
display: flex;
}
</style>