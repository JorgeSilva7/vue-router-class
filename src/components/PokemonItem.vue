<template>
  <div @click="showDetails(pokemon)">
    {{ pokemon.name }}
  </div>
</template>

<script>
export default {
  name: "PokemonItem",
  props: {
    pokemon: {
      type: Object,
      default: null,
    },
  },
  methods: {
    showDetails(pokemon) {
      const pkmnId = pokemon.url.split("/")[6];
      this.$router.push({
        name: "pokemon_details",
        params: {
          id: pkmnId,
        },
      });
    },
  },
};
</script>

<style>
</style>