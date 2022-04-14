<template>
  <div class="condition-wrapper">
    <div>
      <h1>Условие {{ index + 1 }}</h1>
      <select class="condition"
              @change="event => {let value = JSON.parse(event.target.value); condition.title = value.title; this.component = value.component}">
        <option disabled selected value="">
          Выберите условие
        </option>
        <option v-for="condition in model.conditions" v-bind:value="JSON.stringify(condition)">
          {{ condition.title }}
        </option>
      </select>
      <Inputs v-for="(input, indexed) in inputs" :key="input" v-bind:index="indexed + 1" v-bind:chosen="inputComponent"
              v-bind:parameters="condition.inputs[indexed]"/>
      <AddDeleteInputs v-show="this.component !== null" :add-input="addInput" :delete-input="deleteInput" :text="text"/>
    </div>
    <button @click="deleteFunction(index)" class="delete-condition">Удалить условие</button>
  </div>
</template>

<style scoped>
.condition-wrapper {
  border-top: 1px solid lightgray;
  padding: 10px 20px;
  background: #FAFDF1;
  position: relative;
}

select.condition {
  width: 500px;
}

select {
  border-radius: 6px;
  padding: 5px;
}

.delete-condition {
  outline: none;
  border: 1px solid red;
  border-radius: 4px;
  color: red;
  cursor: pointer;
  position: absolute;
  right: 10px;
  bottom: 10px;
  padding: 10px;
  background: white;
}

h1 {
  display: inline;
  margin-right: 40px;
}
</style>

<script>
import Inputs from "./Inputs/Inputs";
import AddDeleteInputs from "./Inputs/AddDeleteInputs";

export default {
  components: {Inputs, AddDeleteInputs},
  data: function () {
    return {
      component: null,
      inputs: [],
      parameters: {}
    }
  },
  computed: {
    inputComponent: function () {
      return this.component
    },
    text: function () {
      switch (this.inputComponent) {
        case "range":
          return "диапазон"
        case "type":
          return "тип"
        case "status":
          return "статус"
      }
    }
  },
  methods: {
    addInput: function () {
      this.inputs.push(Math.random() * this.inputs.length)
      this.condition.inputs.push({})
    },
    deleteInput: function () {
      this.inputs.splice(this.inputs.length - 1, 1)
      this.condition.inputs.splice(this.inputs.length - 1, 1)
    }
  },
  props: {
    model: {},
    condition: {},
    index: 0,
    deleteFunction: () => {
    }
  }
}
</script>
