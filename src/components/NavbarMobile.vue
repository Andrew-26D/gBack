
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '../assets/gbackLogoNavbar.svg'
import telegram from '../assets/telegramLogo.svg'
import locationBtn from '../assets/locationLogo.svg'
import mGlass from '../assets/mGlass.svg'

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
 <div class="header-m">

  <section class="tt">
    <article><button class="seller"><a href="https://app.gback.ir/?rf=gback.ir" target="_blank"> ورود فروشندگان</a></button></article>
    <section>
      <article class="logo"><a href="https://gback.ir/" target="_blank"> <img :src="logo" alt=""></a></article>
      <article></article>
    </section>
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
  scale: .5;
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
  z-index: 999;
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


.header-btn:hover{
border: #d9846d00 2px solid;
}

.seller{
  width: 180px;
  height: 42px;
  border-radius: 15px;
  background-color:rgba(255, 255, 255, 0);
  color: white;
  border: #d9856d 1px solid;
  font-family: 'Yekan', sans-serif;
  font-size: 16px;
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
</style>
