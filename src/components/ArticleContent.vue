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
h1 {
  margin-top: 2vh;
}
p {
  color: #004E3F;
  margin-top: 1vh;
}
.g-image {
  width: 87.5%;
  fit: outside;
}
</style>
