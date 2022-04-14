<template>
  <div class="wrapper">
    <Navigation v-bind:selected="select" :routes="routes"/>
    <div class="fields-wrapper">
      <Parameters v-show="selected === 'Parameters'"/>
      <Questions v-show="selected === 'Questions'"/>
      <Logic v-show="selected === 'Logic'"/>
      <Conditions v-show="selected === 'Conditions'"/>
      <Respondents v-show="selected === 'Respondents'" v-bind:respondents="formData.respondents"/>
      <div class="submit-field">
        <button class="submit-button" @click="submitForm">Отправить</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.fields-wrapper {
  padding-top: 20px;
  border-top: 2px solid lightgreen;
}

div.wrapper {
  box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2);
  border: 1px solid lightgray;
  border-top: none;
  border-bottom: none;
  margin: 40px 40px 0;
}

.submit-field {
  background: #FDFDFD;
  position: relative;
  padding: 20px;
}

.submit-button {
  outline: none;
  border: 2px dotted forestgreen;
  border-radius: 8px;
  padding: 10px;
  background: white;
  margin: 10px auto;
  display: block;
  cursor: pointer;
}
</style>

<script>
import Navigation from "../../components/Surveys/Add/Navigation";
import Parameters from "../../components/Surveys/Add/Parameters";
import Questions from "../../components/Surveys/Add/Questions";
import Conditions from "../../components/Surveys/Add/Conditions";
import Respondents from "../../components/Surveys/Add/Respondents";
import Logic from "../../components/Surveys/Add/Logic"
export default {
  data: function () {
    return {
      select: "",
      formData: {
        parameters: [],
        questions: [],
        logic: [],
        conditions: [],
        respondents: []
      },
      routes: [
        {
          name: "Parameters",
          title: "Параметры",
          func: () => {
            this.select = "Parameters"
          }
        },
        {
          name: "Questions",
          title: "Вопросы",
          func: () => {
            this.select = "Questions"
          }
        },
        {
          name: "Logic",
          title: "Логика",
          func: () => {
            this.select = "Logic"
          }
        },
        {
          name: "Conditions",
          title: "Условия",
          func: () => {
            this.select = "Conditions"
          }
        },
        {
          name: "Respondents",
          title: "Респонденты",
          func: () => {
            this.select = "Respondents"
          }
        },
      ]
    }
  },
  computed: {
    selected: function () {
      return this.select
    }
  },
  methods: {
    submitForm: async function () {
      alert(JSON.stringify(this.formData))
      fetch("https://www.google.com", {method: 'POST', body: JSON.stringify(this.formData)})
      .then((res) => {
        if (!res.ok) {
          alert("Something went wrong")
        }
      })
      .catch((e) => {
        alert(e.message)
      })
    }
  },
  components: {Respondents, Conditions, Questions, Parameters, Navigation, Logic}
}
</script>
