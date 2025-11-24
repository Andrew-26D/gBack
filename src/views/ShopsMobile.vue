<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import NavbarMobile from '../components/NavbarMobile.vue'
import ShopList from '../components/ShopList.vue'
import home from '../assets/home.png'
import shopList from '../assets/shop.png'
import loan from '../assets/loan.png'
import setting from '../assets/setting.png'

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
function detectMobileDevice() {
  const nav = navigator
  if (nav.userAgentData && typeof nav.userAgentData.mobile === 'boolean') {
    return nav.userAgentData.mobile
  }
  const ua = nav.userAgent || ''
  if (/Mobi|Android|iPhone|iPad|iPod|Mobile|Silk/i.test(ua)) return true

  if (/Macintosh/i.test(ua) && 'maxTouchPoints' in navigator && navigator.maxTouchPoints > 1) return true
  return false
}

const isMobileDevice = ref(detectMobileDevice())



</script>

<template>
<NavbarMobile />

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
    <nav v-if="isMobileDevice" class="mobile-bottom-nav">
    <a href="https://gback.ir/" class="navItem">
      <img class="icon" :src="home" alt="">
      <span class="label">خانه</span>
    </a>
    <a href="https://app.gback.ir/?rf=gback.ir" target="_blank" class="navItem">
       <img class="icon" :src="loan" alt="">
      <span class="label">وام</span>
    </a>
    <a href="https://app.gback.ir/?rf=gback.ir" target="_blank" class="navItem">
       <img class="icon" :src="shopList" alt="">
      <span class="label">لیست فروشگاه ها</span>
    </a>
    <a href="https://app.gback.ir/login" class="navItem">
       <img class="icon" :src="setting" alt="">
      <span class="label">تنضیمات</span>
    </a>
  </nav>
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

.body{
  display: flex;
  flex-direction: column;
  background-color:#232122 ;
  height:100% ;
  width: 100%;
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
  width: 100%;
  background-color: #2a2a2a;
  display: flex;
  justify-content: center;
  flex-direction: row-reverse;
  align-items: center;
  z-index: 2000;
  border-top: 1px solid #444;
  backdrop-filter: blur(8px);

}
.navItem:hover{
  color:#8d341a
}
.navItem.active {
  color:#8d341a;
  font-weight: 600;
}
.mobile-bottom-nav .navItem {
  flex: 1;
  color: rgb(183, 183, 183);
  text-align: center;
  font-family: 'Yekan', sans-serif;
  text-decoration: none;
  border: none;
  background: transparent;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

/* .mobile-bottom-nav .icon {
  display: block;
  font-size: 22px;
  line-height: 22px;
} */

.mobile-bottom-nav .label {
  font-size: 11px;
  margin-top: 2px;
}

@media (min-width: 768px) {
  .mobile-bottom-nav {
    display: none;
  }
}
.icon{
  width: 20px;
  height:20px;
}
</style>
