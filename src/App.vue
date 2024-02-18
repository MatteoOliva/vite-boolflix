<script>
import axios from "axios";
import { store } from "./store";

export default {
  data() {
    return {
      store,
      searchedTerm: "ritorno al futuro",
    };
  },

  methods: {
    performSearch() {
      axios
        .get(this.store.api.uri + "/search/movie", {
          params: {
            api_key: store.api.key,
            query: this.searchedTerm,
          },
        })
        .then((response) => {
          console.log(response.data);
        });
    },
  },
};
</script>

<template></template>

<style lang="scss">
@use "./styles/general.scss";
</style>
