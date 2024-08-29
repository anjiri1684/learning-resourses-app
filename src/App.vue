<template>
  <the-header title="RememberMe"></the-header>
  <the-resources></the-resources>
  <add-resources></add-resources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import AddResources from './components/learning-resources/AddResources.vue';
import TheResources from './components/learning-resources/TheResource.vue';

export default {
  components: {
    TheHeader,
    TheResources,
    AddResources,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
