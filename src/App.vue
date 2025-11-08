<script setup>
import logo from '../src/template/لوگو_وام_فوری_جیبک.3fd5cee.svg'
import telegram from '../src/template/download (1).svg'
import locationBtn from '../src/template/download.svg'
import topBanner from '../src/template/GB_HEADER.5bbb1a2.gif'
import mGlass from '../src/template/mGlass.svg'


</script>







<template>
<header>
    <div class="header-t"><img :src="topBanner" alt=""> </div>
    <div class="header-m">
        <article> <button class="header-btn">دریافت وام</button></article>
        <article class="search">
            <section >
              <section class="inputSearch">
                <input type="text" placeholder="جستجوی فروشگاه و کالا">
                <img :src="mGlass" alt="">
              </section>
            <button class="locationBtn">انتخاب استان</button></section>
            <section><img :src="locationBtn" alt=""></section>
        </article>
    <article class="logo"><a href=""> <img :src="logo" alt=""></a></article>
    </div>
 <div class="header-b">
        <section class="lSide">
            <button>ورود فروشگاه</button>
            <a  class="lSide"  href="">
                <p>پشتیبانی آنلاین</p>
                 <img :src="telegram" alt="">
            </a>
        </section>
        <section>
            <nav class="rSide">
                <a href="">درباره جیبک</a>
                <a href="">بلاگ</a>
                <a href="">فروشگاه ها</a>
            </nav>
        </section>
    </div>
</header>
</template>









<style scoped>



html {
  scroll-behavior: smooth;
}
body{
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
 line-height: 24px;
 padding: 24px 150px;
 text-align: justify;
 width: 100%;


}
.header-m section, nav, a{
  color: white;
}



.search{
    height: 52px;
    width: 757px;
    justify-content: end;
    align-items: center;
    border: #555 1.1px solid;
    border-radius: 12px;
    color: wheat;
    display: flex;
    line-height: 24px;
    padding: 0 24px;
    font-family: 'Yekan', sans-serif;
}

.search input{
    width: 100px;
    height: 24px;
    background-color:rgba(255, 255, 255, 0);
    border: none;
    outline: none;
    color: wheat;
    font-family: 'Yekan', sans-serif;
}


.locationBtn{
  display: flex;
    align-items: center;
    justify-content: center;
    width: 140px;
    height: 24px;
    font-family: 'Yekan', sans-serif;
    background-color:rgba(255, 255, 255, 0);
    border: none;
    outline: none;
    color: white;
    border-left: white 1.1px solid;
}

.inputSearch{
  display: flex;
  align-items: center;
  justify-items: center;
  gap: 10px;
}
.header-b{
    height: 84px;
    width: 100%;
    background-color: #2a2a2a;
    color: white;
    line-height: 24px;
    padding: 15px 150px;
    text-align: justify;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-family: 'Yekan', sans-serif;

}
.lSide{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
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
  border: #d9856d 1px solid;
      font-family: 'Yekan', sans-serif;


}

.header-btn:hover{
  border: none;
}

.lSide button{
  width: 188px;
  height: 52px;
  border-radius: 14px;
  padding: 14px;
  background-color:rgba(255, 255, 255, 0);
  color: white;
  border: #d9856d 1px solid;
      font-family: 'Yekan', sans-serif;

}
.lSide button:hover{
  background-color: #8d341a;
  color: white;
  border: none;
  font-family: 'Yekan', sans-serif;
}

.rSide{
  display: flex;
  gap: 20px;
  font-family: 'Yekan', sans-serif;

}
</style>
