<template>
  <div>
    <button :class="classes" @click="onClick">
      Click Me
    </button>
    <div v-if="wasClicked">
      greeting
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class MyButton extends Vue {
  @Prop({ type: Boolean, default: false }) disabled!: boolean;
  @Prop({ type: Boolean, default: false }) wasClicked!: boolean;
  public greeting = "Hello World!";

  get classes(): object {
    return {
      'my-button': true,
      'my-button--disabled': this.disabled
    };
  }

  onClick(): void {
    if (!this.disabled) {
      this.$emit('click');
      this.wasClicked = !this.wasClicked;
    }
  }
}
</script>

<style lang="scss">
.my-button {
  background: black;
  color: white;
  border-radius: 50px;
  padding: 0 20px;
  line-height: 35px;
  border: unset;

  &--disabled {
    background: grey;
    pointer-events: none;
  }
}
</style>
