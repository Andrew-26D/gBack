
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import ShopList from '../components/ShopList.vue'
import navbar from '../components/NavbarDesktop.vue'
import Footer from '../components/Footer.vue'


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
<navbar/>

<div>
  <div class="main">
    <section class="space"></section>
    <section class="bLeft"><ShopList/></section>

    <section class="bRight">
      <ul class="categories">
        <li class="items" > <h5>دسته بندی</h5> </li>
        <li class="items"> <a href="https://gback.ir/storedetail?id=2"> کالای دیجیتال</a></li>
        <li class="items"> <a href="https://gback.ir/storedetail?id=1">لوازم خانگی</a></li>
        <li class="items"> <a href="https://gback.ir/storedetail?id=3">طلا و جواهرات</a></li>
        <li class="items"> <a href="https://gback.ir/storedetail?id=4">فرش</a></li>
      </ul>
    </section>
  </div>
</div>
<Footer/>

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

.main{
  display: flex;
  justify-content: flex-end;
  background-color:#232122 ;
  height:100% ;
  width: 100%;
  margin-top: 100px;
  padding: 200px 80px 0px 110px;
}
.bLeft{
  width: 73%;
}
.bRight{
  width: 15%;
  min-width:200px;
}
.space{
  width: 12%;
}

.bRight li{
display: flex;
justify-content: start;
width: 164.5px;
border-bottom: 1.5px solid #444;
}

.categories{
  display: flex;
  justify-content: start;
  align-items: start;
  flex-direction: column;
 direction: rtl;
  width: 164.5px;
  height: 400px;
  color: white;
  margin: 20px  ;
  list-style: none;
  font-family:'Yekan-Light';
  font-size:16px;

}
.categories a:hover{
color:#C64925 ;
transition:all 0.2s ease-in-out;
}
.categories::selection{
  color:#3D2122 ;

}
.categories h5{
  font-size: 25px;
  font-family:'Yekan';
  font-weight: 200;
  cursor:default;
}
.items{
  padding: 8px 12px;


}
.items:last-child,.items:first-child {
  border-bottom: none;
}

</style>
