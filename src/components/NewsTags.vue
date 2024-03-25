<template>
  <div class="tags">
    <div class="tag blue">в СМИ</div>
    <div class="tag red">акции</div>
  </div>
</template>

<style scoped>
.tags {
  display: flex;
  gap: 10px;
  margin-top: 32px;
}

.tag {
  border: 1px solid transparent;
  border-radius: 20px;
  padding: 4px 12px;
  font-weight: 400;
  font-size: 14px;
  text-align: center;
}

.tag.blue {
  border-color: #5b4481;
  color: #5b4481;
}

.tag.red {
  border-color: #ca2250;
  color: #ca2250;
}

.tag img {
  width: 14px;
  height: 14px;
  margin-right: 5px;
}
</style>
