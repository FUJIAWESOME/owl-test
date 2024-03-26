<script setup>
import { ref, onMounted, watch } from 'vue'
import { useRoute } from 'vue-router'

import NewsCard from './NewsCard.vue'
import NewsBreadcrumbs from './NewsBreadcrumbs.vue'
import NewsTags from './NewsTags.vue'
import axios from 'axios'

const router = useRoute()

defineProps({
  slug: String
})

const responseData = ref({})
const isLoading = ref(true)

onMounted(async () => {
  try {
    const { data } = await axios.get(
      `https://bsk-admin-test.testers-site.ru/api/news/${router.params.id}`
    )
    responseData.value = data.data.result
    isLoading.value = false
  } catch (error) {
    console.log(error)
  }
})

watch(router, async () => {
  isLoading.value = true
  try {
    const { data } = await axios.get(
      `https://bsk-admin-test.testers-site.ru/api/news/${router.params.id}`
    )
    responseData.value = data.data.result
    isLoading.value = false
  } catch (error) {
    console.log(error)
  }
})
</script>

<template>
  <div class="overlay">
    <div class="popup">
      <div class="popup__content">
        <div v-if="isLoading" class="loader"></div>

        <div v-else>
          <NewsBreadcrumbs :currentNewsTitle="responseData.title" />
          <NewsTags :tags="responseData.tags" v-if="responseData.tags" />
          <h1 class="news-title">{{ responseData.title }}</h1>
          <p class="news-date">{{ responseData.date }}</p>

          <div v-for="(item, index) in responseData.content" :key="index">
            <p v-if="item.type === 'text'" class="news-text">{{ item.content }}</p>
            <img
              v-else-if="item.type === 'mediaBlock'"
              class="news-img"
              :src="item.element.src"
              alt="image-content"
            />
          </div>

          <h2 class="news-h2">Следующая статья</h2>

          <NewsCard
            v-if="responseData.next"
            :title="responseData.next.title"
            :date="responseData.next.date"
            :imageUrl="responseData.next.picture"
            :tags="responseData.next.tags"
            :code="responseData.next.code"
          />
        </div>
      </div>
    </div>
  </div>
</template>
