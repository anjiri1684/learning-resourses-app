<template>
  <ul>
    <learning-resource
      v-for="res in resources"
      :id="res.id"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
      >{{
    }}</learning-resource>
  </ul>
</template>

<script>
import LearningRosource from './LearningRosource.vue';

export default {
  inject: ['resources'],
  components: {
    'learning-resource': LearningRosource,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
