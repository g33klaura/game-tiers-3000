<template>
  <div id="app">
    <TierLists />
  </div>
</template>

<script>
  import TierLists from './components/TierLists.vue';

  import './css/zazz.scss';

  export default {
    name: 'App',
    components: {
      TierLists,
    }
  }
</script>
