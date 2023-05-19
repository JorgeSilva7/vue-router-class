<template>
  <div v-if="pokemon">
    <h1>Detalles</h1>
    <img :src="pokemon.sprites.other['official-artwork'].front_default" />
  </div>
  <div v-else>Loading...</div>
</template>

<script>
import { getDetails } from "../services/pokemon.services";
export default {
  name: "PokemonDetail",
  props: {
    id: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      pokemon: null,
    };
  },
  async mounted() {
    const result = await getDetails(this.id);
    this.pokemon = result;
  },
};
</script>

<style>
</style>