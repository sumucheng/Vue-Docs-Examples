<template>
  <Container color="pink">
    <template #header>
      <p>Here might be a page title</p>
    </template>

    <template #default="slotProps">
      <p>{{slotProps.defaultMain}}</p>
    </template>

    <template #footer>
      <p>Here's some contact info</p>
    </template>
  </Container>
</template>

<script>
import Container from "./Container";
export default {
  components: {
    Container
  }
};
</script>