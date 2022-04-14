<template>
  <div class="input-wrapper">
    <h2>Диапазон {{ index }}</h2>
    <span class="tabbed">
    от
    <input type="number" @change="event => parameters.from = event.target.value">
    &nbsp;
    до
    <input type="number" @change="event => parameters.to = event.target.value">
    </span>
  </div>
</template>

<style scoped>
.input-wrapper {
  margin-top: 20px;
  position: relative;
}

.tabbed {
  position: absolute;
  left: 180px;
}

input {
  border-radius: 6px;
  padding: 5px;
  outline: none;
}

h2 {
  display: inline;
  margin-right: 20px;
  font-size: 16px;
}
</style>

<script>
export default {
  props: {
    parameters: {},
    index: 0
  }
}
</script>
