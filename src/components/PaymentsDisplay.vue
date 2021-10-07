<template>
  <div>
    <div v-for="(item, idx) in items" :key="idx">{{ idx }}{{ item }}</div>
  </div>
</template>
 
<script>
</script>


<script>
export default {
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {};
  },
};
</script>

<style>
</style>