<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '../src/template/لوگو_وام_فوری_جیبک.3fd5cee.svg'
import telegram from '../src/template/download (1).svg'
import locationBtn from '../src/template/download.svg'
import topBanner from '../src/template/GB_HEADER.5bbb1a2.gif'
import mGlass from '../src/template/mGlass.svg'
// import webForm from '../src/template/download (2).svg'
// import minimalLogo from '../src/template/logo_gback_loan.669db76.svg'
import ShopList from '../src/ShopList.vue'

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
const showCategories = ref(false)

const toggleMenu = () => {
  showCategories.value = !showCategories.value
}


</script>


<template>
<header>

    <div class="header-t"><a href="https://app.gback.ir/?rf=gback.ir" target="blank"><img :src="topBanner" alt=""></a> </div>
 <div class="header-m">


  <section class="tt">
    <article class="logo"><a href="https://gback.ir/" target="_blank"> <img :src="logo" alt=""></a></article>
    <article><button class="seller"><a href="https://app.gback.ir/?rf=gback.ir" target="_blank"> ورود فروشندگان</a></button></article>
  </section>

        <article class="search">

              <section class="inputSearch">
                <input type="text" placeholder="جستجوی فروشگاه و کالا" dir="rtl">
                <img :src="mGlass" alt="">
              </section>
            <section  class="locationBtn">
            <button>انتخاب استان</button>
              <img :src="locationBtn" alt="">
            </section>

        </article>
    </div>



 <div class="header-b" :class="{ hide: hideHeader }">
        <section class="lSide">

            <a  class="lSide"  href="https://app.gback.ir/?rf=gback.ir " target="blank">
                <p>پشتیبانی آنلاین</p>
                 <img :src="telegram" alt="">
            </a>
        </section>
        <section>
            <nav class="rSide">
                <a href="https://gback.ir/about" >درباره جیبک</a>
                <a href="https://gback.ir/blog/">بلاگ</a>
                <a href="https://gback.ir/storedetail">فروشگاه ها</a>
            </nav>
        </section>
    </div>
</header>
<div class="body">
  <section>

    <transition name="slide-fade">
      <section v-if="showCategories" class="categories-wrapper">
        <ul class="categories">

          <li class="items"><a href="https://gback.ir/storedetail?id=1">لوازم خانگی</a></li>
          <li class="items"><a href="https://gback.ir/storedetail?id=2">کالای دیجیتال</a></li>
          <li class="items"><a href="https://gback.ir/storedetail?id=3">طلا و جواهرات</a></li>
          <li class="items"><a href="https://gback.ir/storedetail?id=4">فرش</a></li>
        </ul>
      </section>
    </transition>
    <ShopList />
</section>
</div>


  <nav class="mobile-bottom-nav">
    <a href="/" class="navItem">
      <span class="icon">🏠</span>
      <span class="label">خانه</span>
    </a>
    <button class="navItem" @click="toggleMenu">
      <span class="icon">📂</span>
      <span class="label">دسته‌بندی‌ها</span>
    </button>
    <a href="https://app.gback.ir/?rf=gback.ir" target="_blank" class="navItem">
      <span class="icon">💰</span>
      <span class="label">دریافت وام</span>
    </a>
    <a href="/account" class="navItem">
      <span class="icon">👤</span>
      <span class="label">حساب</span>
    </a>
  </nav>

<!-- <footer class="footer">
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

</footer> -->
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
}
.header-t{

    width: 100%;
    height: 30px;
    background-color:#454545;
    color: white;
    padding: 10px 0;
    line-height: 24px;
    font-size: 24px;
    display: flex;
    align-items: center;
    justify-content: center;

}
.header-t img{
  width: 90%;
  scale: 2;
}



.header-m {
  left: 0;
  right: 0;
  z-index: 999;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 12px 20px;
  height: 150px;
  text-align: justify;
  background-color: #232122;
  color: white;
flex-direction: column;
  transition: top 0.3s ease-in-out;
}

.tt{

  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;

}


.header-m section, nav, a{
  color: white;
}


.logo{
  scale: .6;
}

.search{
    height: 52px;
    width: 100%;
    display: flex;
    justify-content: end;
    align-items: center;
    background-color:rgba(255, 255, 255, 0);
    border: #555 1.1px solid;
    border-radius: 12px;
    color: wheat;
    line-height: 24px;
    padding: 0 12px;
    font-family: 'Yekan', sans-serif;
    font-size: 12px;
}

.search input{
    height: 24px;
    background-color:rgba(255, 255, 255, 0);
    border: none;
    outline: none;
    color: wheat;
    font-family: 'Yekan', sans-serif;
    font-size: 14px;
}


.locationBtn{
  display: flex;
    align-items: center;
    justify-content: center;
    width: 140px;
    height: 24px;
    color: white;
    border-left: white 1.1px solid;
    margin-left: 15px ;
     cursor: pointer;
     font-size: 10px;

}
.locationBtn button{
      background-color:rgba(255, 255, 255, 0);
     border: none;
    outline: none;
    color: white;
        font-family: 'Yekan', sans-serif;
    font-weight: 400;
    line-height: 1.5;
    cursor: pointer;
     font-size: 14px;
}
.locationBtn img{
  width: 20px;
}
.inputSearch{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  height: 100%;
}
 .header-m{
  position: fixed;
  top: 30px;
  z-index: 999;
}
.header-t{
  position: fixed;
  top: 0;
  z-index: 1000;
}
.header-b{
  position: fixed;
  top: 170px;
  transition: transform 0.3s ease-in-out;
  width: 100%;
  background-color: #2a2a2a;
  color: white;
  padding: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Yekan', sans-serif;

}
.header-b.hide {
  transform: translateY(-100%);
}
.lSide{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    cursor: pointer;
}
.lSide p{
   font-family: 'Yekan', sans-serif;
   font-size:14px;
    cursor: pointer;
    margin-left: 1rem;
}
.header-btn{
  border-radius: 12px;
  margin: 0 6px 0 5px;
  padding: 10px 5px 10px 5px;
  background-color: #c64925;
  color: white;
  text-align: center;
  width: 90px;
  height: 40px;
  border: #d9856d 2px solid;
  font-family: 'Yekan', sans-serif;
  font-size: 14px;
}

.header-btn:hover{
border: #d9846d00 2px solid;
}

.seller{
  width: 90px;
  height: 40px;
  border-radius: 10px;
  background-color:rgba(255, 255, 255, 0);
  color: white;
  border: #d9856d 1px solid;
  font-family: 'Yekan', sans-serif;
  font-size: 12px;
  cursor: pointer;
  text-align: center;
  transition: all 0.3s ease-in-out;

}
.lSide button:hover{
  background-color: #8d341a;
  color: white;
  border: none;
  font-family: 'Yekan', sans-serif;
}

.rSide {
  display: flex;
  gap: 20px;
  font-family: 'Yekan', sans-serif;
  font-size: 12px;
  padding: .5rem 1rem;
}
.body{
  display: flex;
  flex-direction: column;
  background-color:#232122 ;
  height:100% ;
  width: 100%;
  margin-top: 180px;
  padding:  80px 0px 200px;
}
.body >section{
  display: flex;
  justify-content: flex-start;
  align-items: end;
  flex-direction: column;
}




.categories{
direction: rtl;
  width:400px;
  height: 100px;
  background-color:#2a2a2a ;
  color: white;
  display: flex;
  flex-direction: row;
  border-radius: 12px;
  padding: 10px;
  list-style: none;
  font-size: 18px;
}
.categories::selection{
  color:#3D2122 ;
}
.categories p {
  font-size: 22px;
}



.items{
  padding: 8px 12px;
  border-bottom: 1px solid #444;

}
.items:last-child,.items:first-child {
  border-bottom: none;
}


/* .footer{
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
} */


.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.4s ease;
}
.slide-fade-enter-from,
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

.categories-wrapper {
  width:200;

  margin: 10px 25px 10px 15px;
}

.categories {
  display: flex;
  align-items: center;
  justify-content: center;
  direction: rtl;
  width: 100%;
  background-color: #2a2a2a;
  color: white;
  border-radius: 12px;
  padding: 10px;
  list-style: none;
  font-size: 13px;
}

.items {
  padding: 8px 12px;
  border-bottom: 1px solid #444;
}
.items:last-child,
.items:first-child {
  border-bottom: none;
}

.mobile-bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 65px;
  background-color: #2a2a2a;
  display: flex;
  justify-content: space-around;
  align-items: center;
  z-index: 2000;
  border-top: 1px solid #444;
  backdrop-filter: blur(8px);
}

.mobile-bottom-nav .navItem {
  flex: 1;
  color: white;
  text-align: center;
  font-family: 'Yekan', sans-serif;
  text-decoration: none;
  border: none;
  background: transparent;
  cursor: pointer;
}

.mobile-bottom-nav .icon {
  display: block;
  font-size: 22px;
  line-height: 22px;
}

.mobile-bottom-nav .label {
  font-size: 11px;
  margin-top: 2px;
}

@media (min-width: 768px) {
  .mobile-bottom-nav {
    display: none;
  }
}
</style>
