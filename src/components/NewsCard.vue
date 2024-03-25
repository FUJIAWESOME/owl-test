<script setup>
import NewsTags from './NewsTags.vue'
</script>

<template>
  <div class="news-card">
    <div class="news-card__img-box">
      <img class="news-card__img" src="/content.png" alt="content" />
      <p class="news-card__date">06.10.2023</p>
    </div>
    <div class="news-card__info">
      <p class="news-card__title news-h2">
        Правительство продлило «Льготную ипотеку» и расширило «Семейную».
      </p>
      <NewsTags />
    </div>
  </div>
</template>

<style scoped>
.news-card {
  display: flex;
  /* gap: 24px; */
  position: relative;
  background-color: rgb(218, 218, 218, 0.4);

  border-radius: 20px;
  padding: 4px;
  transition: 0.3s;
  cursor: pointer;

  @media (max-width: 865px) {
    flex-direction: column;
  }
}

.news-card__img-box {
  border-radius: 20px;
  overflow: hidden;
}

.news-card__img {
  transition: transform 0.3s ease;

  @media (max-width: 865px) {
    /* flex-direction: column; */
    /* max-height: 400px; */
  }
}

.news-card__title {
  font-size: 24px;
  line-height: 32px;
  margin: 0;
  transition: 0.3s;

  @media (max-width: 660px) {
    font-size: 20px;
  }

  @media (max-width: 564px) {
    font-size: 17px;
    line-height: 22px;
  }

  @media (max-width: 492px) {
    font-size: 15px;
  }
}

.news-card__date {
  position: absolute;
  left: 20px;
  top: 20px;

  background-color: rgba(91, 68, 129, 0.8);
  color: white;
  padding: 8px 16px;
  font-size: 14px;
  font-weight: 500;
  line-height: 14px;
  border-radius: 20px;
}

.news-card__info {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  /* margin-top: 12px; */
  /* margin-bottom: 12px; */
  padding: 12px 0;
  padding-left: 24px;

  @media (max-width: 865px) {
    padding-left: 12px;
  }
}

.news-card:hover .news-card__title {
  color: #ca2250;
}

.news-card:hover {
  box-shadow: 0px 0px 1px 2px rgba(202, 34, 80, 0.05);
}

.news-card:hover .news-card__img-box img {
  transform: scale(1.5);
}
</style>
