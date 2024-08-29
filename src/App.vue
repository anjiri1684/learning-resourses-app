<template>
  <ul>
    <learning-resource
      v-for="res in storedResources"
      :key="res.id"
      >{{
    }}</learning-resource>
  </ul>
</template>

<script>
import LearningResource from './components/learning-resources/LearningRosource.vue';

export default {
  components: {
    // eslint-disable-next-line vue/no-unused-components
    LearningResource,
  },
  data() {
    return {
      storedResources: [
        {
          id: 1,
          title: 'Official Guide',
          description: 'The official Vuejs documentation',
          link: 'https://vuejs.org/',
        },
        {
          id: 2,
          title: 'Vuejs Tutorial',
          description: 'A tutorial for Vuejs',
          link: 'https://www.udemy.com/course/vuejs-2-the-complete-guide/learn/lecture/21526316#questions',
        },
      ],
    };
  },
};
</script>
