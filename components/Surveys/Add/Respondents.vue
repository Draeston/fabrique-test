<template>
  <div>
    <div class="add-survey">Добавить опрос</div>
    <Condition v-for="(condition, index) in conditions" :key="condition" :model="model" v-bind:condition="respondents[index]" v-bind:index="index" :delete-function="deleteFunction"/>
    <AddCondition :add-condition="addCondition" />
  </div>
</template>

<style scoped>
.add-survey {
  padding: 5px 10px 5px 20px;
  color: lightgray;
  font-weight: bold;
}
</style>
<script>
import Condition from "./Condition";
import Range from "./Inputs/Range";
import AddCondition from "./AddCondition";
export default {
  data: function () {
    return {
      model: {
        conditions: [
          {
            title: "Возраст реципиента",
            component: "range"
          },
          {
            title: "Тип карты лояльности",
            component: "type"
          },
          {
            title: "Статус карты лояльности",
            component: "status"
          }
        ]
      },
      conditions: []
    }
  },
  methods: {
    deleteFunction: function (index) {
      this.conditions.splice(index, 1)
      this.respondents.splice(index, 1)
    },
    addCondition: function () {
      this.conditions.push(Math.random() * this.conditions.length)
      this.respondents.push({title: "", inputs: []})
    }
  },
  props: {
    respondents: []
  },
  components: {AddCondition, Condition}
}
</script>
