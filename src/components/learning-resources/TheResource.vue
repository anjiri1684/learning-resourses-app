<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Stored Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import storedResources from './storedResources.vue';
import AddResources from './AddResources.vue';
export default {
  components: {
    storedResources,
    AddResources,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
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
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString(),
        title,
        description,
        link,
      };
      this.storedResources.push(newResource);
      this.selectedTab = 'stored-resources';
      this.$emit('resource-added', newResource);
    },
  },
};
</script>
