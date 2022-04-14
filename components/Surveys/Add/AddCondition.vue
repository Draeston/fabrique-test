<template>
  <div @click="addCondition">
    <img src="/plus.png" alt="">
    <br>
    <p>Нажмите, чтобы добавить новые условия выборки.</p>
    <p>Все условия связываются между собой логическим "И"</p>
  </div>
</template>

<style scoped>
div {
  border: 1px solid green;
  width: 80%;
  margin: 20px auto;
  text-align: center;
  padding: 20px;
  cursor: pointer;
  user-select: none;
}

p {
  color: forestgreen;
}
</style>

<script>
export default {
  props: {
    addCondition: () => {}
  }
}
</script>
