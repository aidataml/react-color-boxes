<template>
  <div>
    <div class="row">
      <div class="col" v-for="(box, index) in boxes" :key="index">
        <Box :color="box.color" :changed="box.changed" />
      </div>
    </div>
    <button class="btn btn-primary mt-3" @click="changeColor">Change</button>
  </div>
</template>

<script>
import Box from './Box.vue';

export default {
  components: {
    Box,
  },
  props: {
    possibleColors: {
      type: Array,
      default: () => ['#0066ff', '##00cc66', '#ff9933', '#cc0000', '#cc33ff'],
    },
    numBoxes: {
      type: Number,
      default: 24,
    },
  },
  data() {
    return {
      boxes: Array.from({ length: this.numBoxes }, () => ({
        color: this.getRandomColor(),
        changed: false,
      })),
    };
  },
  methods: {
    getRandomColor() {
      return this.possibleColors[Math.floor(Math.random() * this.possibleColors.length)];
    },
    changeColor() {
      const randomBoxIndex =
      Math.floor(Math.random() * this.boxes.length);
      this.boxes = this.boxes.map((box, index) => {
        if (index === randomBoxIndex) {
        return { color: this.getRandomColor(), changed: true };
        }
        return { ...box, changed: false };
      });
    },
  },
};
</script>

<style>
  .box-container {
    display: flex;
    flex-wrap: wrap;
    max-width: 420px;
  }
  button {
    margin-top: 20px;
  }
</style>