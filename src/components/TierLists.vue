<template>
  <div class="groot">
    <h1>My Tiers</h1>
    <div class="tiers-grid">
      <div class="loved row-header">Love it</div>
      <div class="liked row-header">Like it</div>
      <div class="disliked row-header">Leave it</div>
      <div class="ondeck row-header">Haven't played</div>

      <!-- Begin draggable tier rows -->
      <!-- Love it row -->
      <draggable
        class="list-group loved-row"
        :list="loved"
        group="titles"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title) in loved"
            :key="title.name"
            :alt="title.name"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              <span>{{ title.name }}</span>
          </div>
      </draggable>

      <!-- Like it row -->
      <draggable
        class="list-group liked-row"
        :list="liked"
        group="titles"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title) in liked"
            :key="title.name"
            :alt="title.name"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              <span>{{ title.name }}</span>
          </div>
      </draggable>

      <!-- Leave it row -->
      <draggable
        class="list-group disliked-row"
        :list="disliked"
        group="titles"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title) in disliked"
            :key="title.name"
            :alt="title.name"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              <span>{{ title.name }}</span>
          </div>
      </draggable>

      <!-- Haven't played row -->
      <draggable
        class="list-group ondeck-row"
        :list="ondeck"
        group="titles"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title) in ondeck"
            :key="title.name"
            :alt="title.name"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              <span>{{ title.name }}</span>
          </div>
      </draggable>
    </div>

    <h2>Games Library</h2>
    <draggable
      class="library-grid list-group"
      :list="titles"
      group="titles"
      @change="log">
        <div
          class="list-group-item"
          v-for="(title) in titles"
          :key="title.name"
          :alt="title.name"
          :style="{ backgroundImage: 'url(' + title.img + ')' }">
            <span>{{ title.name }}</span>
        </div>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable';
import titlesJson from '../assets/titles.json';

export default {
  name: 'TierLists',
  components: {
    draggable,
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
