<template>
  <div>
    <Header />
    <Content />
  </div>
</template>

<script>
import Header from "@/components/template/Header.vue";
import Content from "@/components/template/Content.vue";

export default {
  name: "Home",
  components: {
    Header,
    Content,
  },
};
</script>