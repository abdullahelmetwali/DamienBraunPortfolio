<template>
  <h1>TEST COMPONENT</h1>
  <p :key="link">{{ link }}</p>
</template>
<script>
export default {
  props: ['link']
}
</script>
