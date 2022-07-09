<template>
  <div>
    <title-text />
    <size-form @submit="createBoard" v-if="gameState == 'pending'" />
    <othello-piece :color="1" :size="50" />
  </div>
</template>

<script>
import OthelloPiece from "./components/parts/OthelloPiece.vue";
import TitleText from "./components/parts/TitleText.vue";
import SizeForm from "./components/templates/SizeForm.vue";

export default {
  name: "App",
  components: {
    SizeForm,
    OthelloPiece,
    TitleText,
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

<style scoped>
div {
  width: 500px;
  height: 500px;
  margin: auto;
}
</style>
