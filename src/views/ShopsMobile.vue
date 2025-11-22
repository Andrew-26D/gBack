<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import NavbarMobile from '../components/NavbarMobile.vue'
import ShopList from '../components/ShopList.vue'

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
