
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
<div class="body">
  <section class="bLeft"><ShopList/></section>
  <section class="bRight">
    <ul class="categories">
      <li class="items" > <p>دسته بندی ها</p> </li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=1">لوازم خانگی</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=2"> کالای دیجیتال</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=3">طلا و جواهرات</a></li>
      <li class="items"> <a href="https://gback.ir/storedetail?id=4">فرش</a></li>
    </ul>
  </section>
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

.body{
  display: flex;
  justify-content: flex-end;
  background-color:#232122 ;
  height:100% ;
  width: 100%;
  margin-top: 100px;
  padding: 200px 80px 0px 110px;
}
.bLeft{
  width: 80%;
}
.bRight{
  width: 20%;
}
.categories{
 direction: rtl;
  width: 200px;
  height: 400px;
  background-color:#2a2a2a ;
  color: white;
  margin: 20px 10px 20px ;
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

</style>
