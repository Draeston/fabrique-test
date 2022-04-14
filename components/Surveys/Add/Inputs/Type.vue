<template>
  <div class="input-wrapper">
    <h2>Тип {{ index }}</h2>
    <select @change="e => parameters.type = e.target.value">
      <option value="" selected disabled>Выберите тип</option>
      <option value="Platinum">Platinum</option>
      <option value="Gold">Gold</option>
      <option value="Silver">Silver</option>
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
export default {
  props: {
    parameters: {},
    index: 0
  }
}
</script>
