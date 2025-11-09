<script setup>
import { ref, onMounted } from 'vue'

const shops = ref([])
const loading = ref(false)
const offset = ref(0)
const limit = 12
const hasMore = ref(true)

const apiUrl = 'https://api.gback.ir/loyalty/store_loyalty_plan/list_create/'

const fetchShops = async () => {
  if (loading.value || !hasMore.value) return
  loading.value = true

  try {
    const res = await fetch(
      `${apiUrl}?store__category=&offset=${offset.value}&limit=${limit}&store__city__province=&search=&store__tags=&ordering=priority,id`
    )
    const data = await res.json()

    if (data.results && data.results.length > 0) {
      const mapped = data.results.map(item => ({
        id: item.store.id,
        name: item.store.name_fa || 'بدون نام',
        logo: item.store.icon_url || '',
        image: item.store.image || '',
        address: item.store.address || 'بدون آدرس'
      }))
      shops.value.push(...mapped)
      offset.value += limit
    } else {
      hasMore.value = false
    }
  } catch (err) {
    console.error('Error fetching shops:', err)
  } finally {
    loading.value = false
  }
}

const handleScroll = () => {
  const { scrollTop, scrollHeight, clientHeight } = document.documentElement
  if (scrollTop + clientHeight >= scrollHeight - 200) {
    fetchShops()
  }
}

onMounted(() => {
  fetchShops()
  window.addEventListener('scroll', handleScroll)
})
</script>

<template>
  <section class="shopList">
    <div class="cards">
      <div class="card" v-for="shop in shops" :key="shop.id">
        <!-- Header: store name left, logo right -->
        <div class="cardHeader">
          <h5 class="storeName">{{ shop.name }}</h5>
          <img class="storeLogo" :src="shop.logo" alt="logo" />
        </div>

        <img v-if="shop.image" :src="shop.image" alt="shop image" class="shopImage" />


        <p class="shopAddress">{{ shop.address }}</p>
      </div>
    </div>


    <div v-if="loading" class="loader"></div>
  </section>
</template>

<style scoped>
.shopList {
  width: 100%;
  min-height: 400px;
  background-color: #232122;
  padding: 2rem;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  justify-items: center;
  width: 100%;
  max-width: 1200px;
}

.card {
  background-color: #2a2a2a;
  padding: 16px;
  border-radius: 12px;
  width: 100%;
  transition: transform 0.2s;
}

.card:hover {
  transform: translateY(-5px);
}


.cardHeader {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
  flex-direction: row-reverse;
}

.storeName {
  font-size: 1.2rem;
  margin: 0 8px 0 0;
  font-weight: 100;
}

.storeLogo {
  width: 40px;
  height: 40px;
  object-fit: contain;
  border-radius: 50%;
}


.shopImage {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 10px;
}


.shopAddress {
  font-size: 0.9rem;
  color: #ccc;
  text-align: right;
}


.loader {
  display: inline-grid;
  padding: 5px;
  filter: blur(4px) contrast(12);
  margin-top: 1rem;
}
.loader:before {
  content: "";
  height: 40px;
  aspect-ratio: 3;
  --c: #8d000000 64%,#8f0000 66% 98%,#85000000 101%;
  background:
    radial-gradient(35% 146% at 50% 159%,var(--c)) 0 0,
    radial-gradient(35% 146% at 50% -59%,var(--c)) 100% 100%;
  background-size: calc(200%/3) 50%;
  background-repeat: repeat-x;
  background-color: #23212200;
  animation: l11 .8s infinite linear;
}
@keyframes l11 {
  to {background-position: -200% 0,-100% 100%}
}
</style>
