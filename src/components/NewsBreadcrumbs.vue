<template>
  <ul class="breadcrumbs">
    <li>главная</li>
    <li class="breadcrumbs-dot">&bull;</li>
    <li>новости</li>
    <li class="breadcrumbs-dot">&bull;</li>
    <li class="highlighted">Средняя ставка по ипотеке в России превысила 8%</li>
  </ul>
</template>

<style scoped>
.breadcrumbs {
  display: flex;
  width: 100%;
  gap: 5px;
  text-transform: uppercase;
  font-weight: 500;
  color: #423f3f;
  white-space: nowrap;
  overflow-x: auto;
}

.breadcrumbs::-webkit-scrollbar {
  display: none;
}

.breadcrumbs {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

.breadcrumbs li:not(:last-child):not(.breadcrumbs-dot) {
  cursor: pointer;
}

.breadcrumbs li:hover:not(:last-child):not(.breadcrumbs-dot) {
  color: #ca2250;
}

.breadcrumbs li.highlighted {
  color: #423f3fb2;
}
</style>
