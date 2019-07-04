<template>
  <div>
    <app-header v-on:renew="renewEvent" v-bind:propsdata="str">app</app-header>
  </div>
</template>



<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  data: function() {
    return {
      str: "my header"
    };
  },
  components: {
    "app-header": AppHeader
  },
  methods: {
    renewEvent: function() {
      this.str = "change string";
    }
  }
};
</script>

<style>
</style>
