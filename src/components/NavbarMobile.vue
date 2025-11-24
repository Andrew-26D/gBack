
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '../assets/gbackLogoNavbar.svg'
import locationBtn from '../assets/locationLogo.svg'
import mGlass from '../assets/mGlass.svg'
import menu from '../assets/burger-menu.png'
import insta from '../assets/insta.png'
import linkedin from '../assets/linkedin.png'

// Fixed header
const fixedHeader = ref(false)
const handleScroll = () => {
  fixedHeader.value = window.scrollY > 100
}
onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))

// Sidebar
const sidebarOpen = ref(false)
const openSidebar = () => sidebarOpen.value = true
const closeSidebar = () => sidebarOpen.value = false
</script>



<template>
<header>

<div class="header-t">
  <section class="tt">
    <article>
      <button class="seller">
        <a href="https://app.gback.ir/?rf=gback.ir" target="_blank">ورود فروشندگان</a>
      </button>
    </article>

    <section class="rSide">
      <article class="logo">
        <a href="https://gback.ir/" target="_blank"><img :src="logo" alt=""></a>
      </article>

      <article>
        <a @click.prevent="openSidebar"><img class="icon" :src="menu" alt=""></a>
      </article>
    </section>
  </section>
</div>

<div class="header" :class="{ fixed: fixedHeader }">
  <article class="search">
    <section class="inputSearch">
      <input type="text" placeholder="جستجوی فروشگاه و کالا" dir="rtl">
      <img :src="mGlass" alt="">
    </section>
    <section class="locationBtn">
      <button>انتخاب استان</button>
      <img :src="locationBtn" alt="">
    </section>
  </article>
</div>
</header>

<div 
  v-if="sidebarOpen" 
  class="overlay" 
  @click="closeSidebar">
</div>

<aside class="sidebar" :class="{ open: sidebarOpen }">
  
  <button class="closeBtn" @click="closeSidebar">×</button>

  <nav class="menuList">
    <a href="#">فروشگاه‌ها</a>
    <a href="#">فروشندگان</a>
    <a href="#">وبلاگ</a>
  </nav>

  <div class="socials">
    <a href="https://www.instagram.com/gback.ir/?igsh=dGxwMTRkOW53MDRv"><img :src="insta" alt="Instagram"></a>
    <a href="#"><img :src="linkedin" alt="LinkedIn"></a>
  </div>

</aside>
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
  width: 100%  ;
  background-color: #232122;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
  flex-direction: row;
}
.logo{
  scale: 0.5;
}
.header{
  background-color: #232122;
  display: flex;
  align-items: center;
  justify-content: center;

}
.tt {
  display: flex;
  align-items: center;
  justify-content: space-between; /* puts left item and right items apart */
  width: 100%;
  margin-inline: 35px;
}

.rSide {
  display: flex;
  justify-content: end;
  align-items: center;
}
.seller{
  width: 130px;
  height: 42px;
  border-radius: 15px;
  background-color:rgba(255, 255, 255, 0);

  border: #d9856d 1px solid;
  font-family: 'Yekan', sans-serif;
  font-size: 16px;
  cursor: pointer;
  text-align: center;
  transition: all 0.3s ease-in-out;
}
.seller a {
  color: white;
}
.seller:hover{
  background-color: #8d341a;
  color: white;
  border: none;
  font-family: 'Yekan', sans-serif;
}
.icon{
  width: 20px;
  height: 15px;
}

.header.fixed {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 9999;
  background-color: #232122;
  padding-block: 10px;
}


.search{
    height: 52px;
    width: 90%;
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
.header-btn:hover{
border: #d9846d00 2px solid;
}
.socials img {
  width: 32px;
  height: 32px;
}
.socials {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding-bottom: 20px;
}

.menuList a {
  color: white;
  font-size: 18px;
  padding: 12px 0;
  display: block;
  text-decoration: none;
}
.closeBtn {
  background: none;
  border: none;
  font-size: 32px;
  color: white;
  cursor: pointer;
  align-self: flex-end;
}

.sidebar.open {
  right: 0;
}
.sidebar {
  position: fixed;
  top: 0;
  right: -260px;
  width: 260px;
  height: 100%;
  background-color: #1d1c1c;
  box-shadow: -2px 0 10px rgba(0,0,0,0.3);
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  z-index: 9999;
  transition: right 0.3s ease-in-out;
}
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.5);
  z-index: 9000;
}


</style>
