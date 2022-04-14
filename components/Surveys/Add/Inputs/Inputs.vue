<template>
  <div>
    <Range v-show="chosen === 'range'" v-bind:parameters="parameters" v-bind:index="index"/>
    <Status v-show="chosen === 'status'" v-bind:parameters="parameters" v-bind:index="index"/>
    <Type v-show="chosen === 'type'" v-bind:parameters="parameters" v-bind:index="index"/>
  </div>
</template>

<style>
</style>

<script>
import Range from "./Range";
import Status from "./Status";
import Type from "./Type";

export default {
  components: {Type, Status, Range},
  props: {
    chosen: "",
    parameters: {},
    index: 0
  }
}
</script>
