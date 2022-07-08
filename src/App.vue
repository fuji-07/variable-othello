<template>
  <size-form @submit="createBoard" v-if="gameState == 'pending'" />
</template>

<script>
import SizeForm from "./components/templates/SizeForm.vue";

export default {
  name: "App",
  components: {
    SizeForm,
  },
  data() {
    return {
      gameState: "pending",
    };
  },
  methods: {
    createBoard(width, height) {
      console.log(width, height);
      this.gameState = "play";
    },
  },
};
</script>

<style>
</style>
