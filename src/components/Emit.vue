<template>
  <div class="emit">
    <h1>{{emsg}}</h1>
    <div>
      <label>Camera Z position</label>
      <input type="range" v-model="camZdeg" min="0" max="359">
      <span>{{camZdeg}}</span>
    </div>
  </div>
</template>

<script>
  /* eslint-disable no-console */
  import Vue from 'vue';
  import VueEvents from 'vue-events';

  Vue.use(VueEvents);

  export default {
    name: 'emit',
    data() {
      return {
        emsg: 'emit',
        camZdeg: 0,
      };
    },
    watch: {
      camZdeg(nDeg) {
        console.log('emit');
        this.$events.emit('cameraDeltaX', nDeg);
      },
    },
  };
</script>
