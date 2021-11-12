<template>
  <div class="flex items-center justify-between w-full">
    <header
      class="
        items-center
        flex-wrap
        md:p-4
        lg:p-4
        w-full
        bg-blue-500
        shadow
        sm:text-sm
        block
      "
    >
      <div class="container mx-auto flex p-4 flex-col md:flex-row items-center">
        <div
          class="
            flex
            lg:w-full
            sm:w-full
            flex-wrap
            items-center
            md:ml-auto
            inline-flex
            space-x-2
            justify-center
          "
        >
          <input
            v-model="text"
            class="
              appearance-none
              bg-transparent bg-white
              hover:bg-gray-200
              rounded
              py-3
              mt-6
              leading-tight
              focus:outline-none
            "
            type="text"
            placeholder="First name"
            aria-label="Full name"
          />
          <input
            class="
              appearance-none
              bg-transparent bg-white
              hover:bg-gray-200
              rounded
              py-3
              mt-6
              leading-tight
              focus:outline-none
            "
            type="text"
            placeholder="Last name"
            aria-label="Full name"
          />
          <input
            class="
              appearance-none
              bg-transparent bg-white
              hover:bg-gray-200
              rounded
              py-3
              mt-6
              leading-tight
              focus:outline-none
            "
            type="text"
            placeholder="Participation"
            aria-label="Full name"
          />
          <button
            @click.prevent="sendMessage()"
            class="
              inline-block
              text-sm
              px-8
              py-3
              mt-6
              leading-none
              border
              rounded
              text-white
              border-white
              hover:border-transparent hover:text-teal hover:bg-blue-900
            "
          >
            Send
          </button>
        </div>
      </div>
    </header>
  </div>
</template>

<script>
import Bus from "../bus";

export default {
  data: () => ({
    text: "",
  }),
  methods: {
    sendMessage() {
      Bus.$emit("send:message", this.text);
    },
  },
};
</script>

<style>
</style>