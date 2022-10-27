<template>
  <v-row>
    <v-container class="game-wrapper">
      <v-row>
        <v-col>
          <game></game>
        </v-col>
      </v-row>
    </v-container>
  </v-row>
</template>

<script>
import Game from '@/components/Game.vue'
export default {
  name: 'IndexPage',
  components:{
    Game
  }
}
</script>
<style scoped>
.game-wrapper{
  display: flex;
  min-height: 80vh;
  margin: 5vh 0;
}

</style>
