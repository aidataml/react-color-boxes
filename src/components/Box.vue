<template>
  <div class="box" :style="{ backgroundColor: color }">
    <span v-if="changed">Changed!</span>
  </div>
</template>

<script>
export default {
  props: {
    color: String,
    changed: Boolean,
  },
};
</script>

<style>
.box {
  width: 100px;
  height: 100px;
  margin: 10px;
  display: flex;
  flex-wrap: wrap;
  background-color: rgb(82, 82, 82);
  justify-content: center;
  align-items: center;
}
</style>  