<template>
  <div id="app">
    <MyButton />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import MyButton from './components/MyButton/MyButton.vue';

@Component({
  components: {
    MyButton,
  },
})
export default class App extends Vue { }
</script>

<style lang="scss">
#app {
  text-align: center;
  margin-top: 60px;
}
</style>
