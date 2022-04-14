<template>
  <ul>
    <li v-for="route in routes" @click="route.func(); handleClick(route.name);" v-bind:id="route.name">{{ route.title }}</li>
  </ul>
</template>

<style>
ul {
  list-style-type: none;
}

li {
  cursor: pointer;
  user-select: none;
  display: inline-block;
  color: green;
  padding: 15px;
  text-align: center;
}
</style>

<script>
export default {
  mounted() {
    this.routes.forEach(item => {
      document.getElementById(item.name).style.width = `calc(100%/${this.routes.length})`})
  },
  methods: {
    handleClick: function (id) {
      this.routes.forEach(item => {
        document.getElementById(item.name).style.color = "green";
        document.getElementById(item.name).style.border = "none"
      })
      document.getElementById(id).style.borderBottom = "2px solid yellowgreen"
      document.getElementById(id).style.color = "black"
    }
  },
  props: {
    routes: [],
    selected: "",
    next: () => {}
  }
}
</script>
