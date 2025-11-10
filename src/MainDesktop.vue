<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '../src/template/لوگو_وام_فوری_جیبک.3fd5cee.svg'
import telegram from '../src/template/download (1).svg'
import locationBtn from '../src/template/download.svg'
import topBanner from '../src/template/GB_HEADER.5bbb1a2.gif'
import mGlass from '../src/template/mGlass.svg'
import webForm from '../src/template/download (2).svg'
import minimalLogo from '../src/template/logo_gback_loan.669db76.svg'
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


</script>


<template>
<header>

    <div class="header-t"><a href="https://app.gback.ir/?rf=gback.ir" target="blank"><img :src="topBanner" alt=""></a> </div>
    <div class="header-m">
        <article> <button class="header-btn"><a href="https://app.gback.ir/?rf=gback.ir" target="blank">دریافت وام</a></button></article>

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
    <article class="logo"><a href="https://gback.ir/" target="_blank"> <img :src="logo" alt=""></a></article>
    </div>
 <div class="header-b" :class="{ hide: hideHeader }">
        <section class="lSide">
            <button><a href="https://app.gback.ir/?rf=gback.ir" target="_blank"> ورود فروشندگان</a></button>
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
  <ShopList />
  <section >
    <ul class="categories">
      <li class="items" > <p>دسته بندی ها</p> </li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=1">لوازم خانگی</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=2"> کالای دیجیتال</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=3">طلا و جواهرات</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=4">فرش</a></li>
    </ul>
  </section>
</div>

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
}
.header-t{

    width: 100%;
    height: 57px;
    background-color:#454545;
    color: white;
    padding: 10px 0;
    line-height: 24px;
    font-size: 24px;
    align-items: center;
    justify-content: center;

}
.header-t img{
  width: 100%;



}
.header-m{
    background-color:#232122;
color: white;
 align-items: center;
 display: flex;
 justify-content: space-between;

 padding: 24px 150px;
 text-align: justify;
 width: 100%;
 height: 100px;
}
.header-m section, nav, a{
  color: white;
}

.logo{
  margin-left: 62px;
}

.search{
    height: 52px;
    width: 757px;
    display: flex;
    justify-content: end;
    align-items: center;
    background-color:rgba(255, 255, 255, 0);
    border: #555 1.1px solid;
    border-radius: 12px;
    color: wheat;
    line-height: 24px;
    padding: 0 24px;
    font-family: 'Yekan', sans-serif;
}
.search input{
    height: 24px;
    background-color:rgba(255, 255, 255, 0);
    border: none;
    outline: none;
    color: wheat;
    font-family: 'Yekan', sans-serif;
    font-size: 18px;
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

}
.locationBtn button{
      background-color:rgba(255, 255, 255, 0);
     border: none;
    outline: none;
    color: white;
        font-family: 'Yekan', sans-serif;
    font-size: 1.2rem;
    font-weight: 400;
    line-height: 1.5;
    cursor: pointer;
}
.locationBtn img{
  width: 25px;
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
  top: 55px;
  z-index: 999;
}
.header-t{
  position: fixed;
  top: 0;
  z-index: 1000;
}
.header-b{
  position: fixed;
  top: 150px;
  transition: transform 0.3s ease-in-out;
  width: 100%;
  background-color: #2a2a2a;
  color: white;
  line-height: 24px;
  padding: 15px 150px;
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
   font-size:18px;
    cursor: pointer;
    margin-left: 1rem;
}
.header-btn{
  border-radius: 14px;
  line-height: 24px;
  margin: 0 24px 0 0;
  padding: 14px;
  background-color: #c64925;
  color: white;
  text-align: center;
  width: 185px;
  height: 52px;
  border: #d9856d 2px solid;
      font-family: 'Yekan', sans-serif;
      font-size: 16px;
}

.header-btn:hover{
border: #d9846d00 2px solid;
}

.lSide button{
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
  font-size: 20px;
  padding: .5rem 1rem;
}
.body{
  display: flex;
  justify-content: flex-end;
  background-color:#232122 ;
  height:100% ;
  width: 100%;
  margin-top: 100px;
  padding: 200px 80px 0px 200px;
}
.categories{
  position: fixed;
  right: 10px;
direction: rtl;
  width: 200px;
  height: 400px;
  background-color:#2a2a2a ;
  color: white;
  margin: 20px;
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
