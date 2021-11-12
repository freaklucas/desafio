<template>
  <div class="flex">
    <div class="flex flex-col h-screen m-auto items-center mt-12">
      <div
        v-for="des in title"
        :key="des"
        class="font-semibold text-center text-3xl text-gray-700"
      >
        {{ des.text }}
      </div>
      <div
        v-for="des in description"
        :key="des"
        class="text-center text-gray-700 mt-6"
      >
        {{ des.text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Content",
  data() {
    return {
      title: [{ text: "DATA" }],
      description: [
        { text: "Lorem ipsum dolor si amet, consectetur adipiscing elit." },
      ],
    };
  },
};
</script>