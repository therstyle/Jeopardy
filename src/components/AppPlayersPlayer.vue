<template>
  <ul class="player-list">
    <player-card
    v-for="(player, index) in getPlayers" :key="index"
    :player="player"
    ></player-card>
  </ul>
</template>

<script>
import PlayerCard from './layout/PlayerCard.vue';

export default {
  name: 'player',
  components: {
    PlayerCard
  },
  computed: {
    getPlayers: {
      get() {
        return this.$store.getters.getPlayers;
      },
      set(value) {
        this.$store.commit('editPlayer', value);
      }
    }
  }
}
</script>