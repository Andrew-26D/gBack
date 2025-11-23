<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '../assets/gbackLogoNavbar.svg'
import telegram from '../assets/telegramLogo.svg'
import locationBtn from '../assets/locationLogo.svg'
import topBanner from '../assets/gbackGifHeader.gif'
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
  <div class="header-t"><a href="https://app.gback.ir/?rf=gback.ir" target="blank"><img :src="topBanner" alt=""></a> </div>



 <div class="header-m">

    <section class="btnSpace">
      <article><button class="header-btn"><a href="https://app.gback.ir/?rf=gback.ir" target="_blank"> دریافت وام</a></button></article>
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

        <section class="logoSpace">
          <article class="logo"><a href="https://gback.ir/" target="_blank"> <img :src="logo" alt=""></a></article>
        </section>
    </div>



 <div class="header-b" :class="{ hide: hideHeader }">

        <section class="lSide">

            <article><button class="seller"><a href="https://app.gback.ir/?rf=gback.ir" target="_blank"> ورود فروشندگان</a></button></article>

            <a  class="support"  href="https://app.gback.ir/?rf=gback.ir " target="blank">
                <p>پشتیبانی آنلاین</p>
                 <img :src="telegram" alt="">
            </a>
        </section>

        <section class="space-1"></section>
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
    position: fixed;
    top: 0;
    z-index: 1000;

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
 position: fixed;
top: 55px;
z-index: 999;
}
.header-m section, nav, a{
  color: white;
}
.logoSpace{
  display: flex;
  justify-content: end;
  width: 13%;
  min-width: 170px;
}
.btnSpace{
  width: 13%;
  min-width: 200px;
}

.logo{
  margin-left: 62px;
}

.search{
  min-width: 400px;
    height: 52px;
    width: 74%;
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
.header-b{
  position: fixed;
  top: 150px;
  transition: transform 0.3s ease-in-out;
  width: 100%;
  background-color: #2a2a2a;
  color: white;
  line-height: 24px;
  padding: 24px 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Yekan', sans-serif;

}
.header-b.hide {
  transform: translateY(-100%);
}

.lSide{
  min-width: 100px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 5px;
    cursor: pointer;
    width: 22%;

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
  font-size: 20px;
}

.header-btn:hover{
border: #d9846d00 2px solid;
}

.lSide button{
  width: 185px;
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
.space-1{
  width: 58%;
}
.support{
  display: flex;
  justify-content: center;
  text-align: center;
  align-items: center;
  gap: 5px;
}
.support p{
   font-family: 'Yekan', sans-serif;
   font-size:22px;
    cursor: pointer;
    margin-left: 1rem;
}

.rSide {
  width: 20%;
  min-width: 280px;
  display: flex;
  justify-content: end;
  gap: 20px;
  font-family: 'Yekan', sans-serif;
  font-size: 20px;
  padding: .5rem 1rem;
  padding-right: 0;
}
</style>
