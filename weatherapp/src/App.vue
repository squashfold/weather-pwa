<template>
  <div>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/settings">Settings</router-link>
      {{ $store.getters.userUnits }}
    </div>
    <LocationFinder />
    <router-view />
  </div>
</template>


<script>
// @ is an alias to /src

import store from "@/store/index";
import { reactive } from "vue";

import LocationFinder from "@/components/LocationFinder";

export default {
  name: "Settings",
  components: {
    LocationFinder,
  },
  methods: {},
  setup() {
    /**
     * Set state
     */
    const state = reactive({});

    store.commit("initialiseStore");

    return {
      state,
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
