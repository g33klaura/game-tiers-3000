<template>
  <div class="groot">
    <h1>My Tiers</h1>
    <div class="tiers-grid">
      <div class="loved row-header">
        Love it
      </div>
      <div class="liked row-header">
        Like it
      </div>
      <div class="disliked row-header">
        Leave it
      </div>
      <div class="ondeck row-header">
        Haven't played
      </div>
      <div class="loved-row">Loved these</div>
      <div class="liked-row">Liked these</div>
      <div class="disliked-row">Didn't like these</div>
      <div class="ondeck-row">Haven't played these</div>
    </div>

    <h2>Games Library</h2>
    <div class="library-grid">
      <!-- games go here -->
    </div>
  </div>
</template>

<script>
// import draggable from 'vuedraggable';
import titlesJson from '../assets/titles.json';

export default {
  name: 'TierLists',
  components: {
    // draggable,
  },
  data() {
    return {
      titles: titlesJson,
      loved: [],
      liked: [],
      disliked: [],
      ondeck: [],
    }
  },
  methods: {
    log: function (evt) {
      window.console.log(evt);
    }
  },
}
</script>
