<template>
  <div v-html="content" />
</template>

<script>
export default {
  props: {
    content: String
  }
};
</script>

<style>
h2 {
  margin-top: 4vh;
}
p {
  color: #004E3F;
  padding-bottom: 3vh;
}
.g-image {
  width: 87.5%;
}
</style>
