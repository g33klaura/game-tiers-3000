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

      <!-- Begin draggable tier rows -->
      <!-- Love it row -->
      <draggable
        class="list-group loved-row"
        :list="loved"
        group="titles"
        style="border: 1px solid red;"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title, index) in loved"
            :key="title.name"
            :alt="title.name"
            style="border: 1px solid magenta;"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
            {{ title.name }} {{ index }}
          </div>
      </draggable>

      <!-- Like it row -->
      <draggable
        class="list-group liked-row"
        :list="liked"
        group="titles"
        style="border: 1px solid red;"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title, index) in liked"
            :key="title.name"
            :alt="title.name"
            style="border: 1px solid magenta;"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
            {{ title.name }} {{ index }}
          </div>
      </draggable>

      <!-- Leave it row -->
      <draggable
        class="list-group disliked-row"
        :list="disliked"
        group="titles"
        style="border: 1px solid red;"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title, index) in disliked"
            :key="title.name"
            :alt="title.name"
            style="border: 1px solid magenta;"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              {{ title.name }} {{ index }}
          </div>
      </draggable>

      <!-- Haven't played row -->
      <draggable
        class="list-group ondeck-row"
        :list="ondeck"
        group="titles"
        style="border: 1px solid red;"
        @change="log">
          <div
            class="list-group-item"
            v-for="(title, index) in ondeck"
            :key="title.name"
            :alt="title.name"
            style="border: 1px solid magenta;"
            :style="{ backgroundImage: 'url(' + title.img + ')' }">
              {{ title.name }} {{ index }}
          </div>
      </draggable>
    </div>

    <h2>Games Library</h2>
    <!-- <div class="library-grid"></div> -->
    <draggable
      class="library-grid list-group"
      :list="titles"
      group="titles"
      @change="log">
        <div
          class="list-group-item"
          v-for="(title, index) in titles"
          :key="title.name"
          :alt="title.name"
          style="border: 1px solid lime;"
          :style="{ backgroundImage: 'url(' + title.img + ')' }">
          {{ title.name }} {{ index }}
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
