<template>
  <div class="input-wrapper">
    <h2>Статус {{ index }}</h2>
    <select @change="e => parameters.status = e.target.value">
      <option value="" selected disabled>Выберите статус</option>
      <option value="Active">Активна</option>
      <option value="Non-active">Неактивна</option>
    </select>
  </div>
</template>

<style scoped>
.input-wrapper {
  margin-top: 20px;
  position: relative;
}

h2 {
  display: inline;
  margin-right: 20px;
  font-size: 16px;
}

select {
  position: absolute;
  left: 180px;
  width: 200px;
  padding: 5px;
  border-radius: 6px;
}
</style>

<script>
import Search from "../../../Search";
export default {
  components: {Search},
  props: {
    parameters: {},
    index: 0
  }
}
</script>
