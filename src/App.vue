<template>
  <div id="app">
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
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

import './css/zazz.scss';

export default {
  name: 'App',
  components: {
    // HelloWorld
  }
}
</script>
