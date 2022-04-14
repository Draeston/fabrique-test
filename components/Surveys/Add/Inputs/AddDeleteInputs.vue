<template>
  <div>
    <button @click="addInput" class="add">
      Добавить {{ text }}
    </button>
    <button @click="deleteInput" class="delete">
      Удалить {{ text }}
    </button>
  </div>
</template>

<style scoped>
div {
  margin-top: 20px;
  user-select: none;
}

button {
  outline: none;
  border-radius: 4px;
  padding: 10px;
  background: white;
  cursor: pointer;
}

button.delete {
  color: red;
  border: 1px solid red;
}

button.add {
  color: lightgreen;
  border: 1px solid lightgreen;
}
</style>

<script>
export default {
  props: {
    addInput: () => {},
    text: "",
    deleteInput: () => {}
  }
}
</script>
