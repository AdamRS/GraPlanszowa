<template>
<div class="container">
  <div class="leftMenu">
    <app-Cube></app-Cube>
  </div>
  <div class="rightMenu">
        <app-Game-Board></app-Game-Board>
  </div>
</div>

</template>

<script>
    import Cube from './components/Cube.vue';
    import GameBoard from './components/GameBoard.vue'


export default {
  components: {
    appCube: Cube,
    appGameBoard: GameBoard,
  }
  
}
</script>

<style scoped>

.container {
    max-width: 1100px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    grid-gap: 3px;
    margin: 0 auto;
}
.leftMenu {
    width: 500px;
    grid-column: 1;
    grid-row: 1;
}

.rightMenu {
    width: 550px;
    grid-column: 2;
    grid-row: 1;
}

</style>
