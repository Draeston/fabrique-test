<template>
  <div>
    <input type="text" placeholder="Поиск по системе">
    <img src="/search.png" alt="">
  </div>
</template>

<style scoped>
div {
  padding: 10px;
  position: relative;
  border: 1px solid lightgray;
  border-radius: 6px;
}

input {
  border: none;
  height: 100%;
  width: 90%;
  outline: none;
}

img {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translate(0, -50%);
  height: calc(100% - 20px) ;
  width: auto;
}
</style>

