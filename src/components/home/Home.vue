<template>
  <div>
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
        <div
          class="container mx-auto flex p-4 flex-col md:flex-row items-center"
        >
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
              v-model="lastName"
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
              @click.prevent="submit()"
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
    <div class="flex flex-col h-screen m-auto items-center mt-12">
      <div class="flex align-center mt-12">
        <div class="lg:w-2/3 md:w-2/3 mr-8 ml-4 sm:px-6 lg:px-4 center">
          <div class="flex">
            <div class="flex-nowrap ml-16">
              <form class="w-full center max-w-lg mr-8">
                <div class="flex flex-row -mx-5 mb-6"></div>
              </form>
            </div>
          </div>
          <div class="card-table">
            <div class="flex mb-12">
              <table
                class="
                  roundend-t-sm
                  text-sm
                  w-5/6
                  mx-auto
                  font-mono
                  text-gray-800
                "
              >
                <tr class="text-left border-b-2 border-gray-300">
                  <th class="px-4 py-3">Code</th>
                  <th class="px-4 py-3">First name</th>
                  <th class="px-4 py-3">Last name</th>
                  <th class="px-4 py-3">Participation</th>
                </tr>
                <tr
                  v-for="(message, index) in messageList"
                  :item="message"
                  :key="index"
                  class="bg-gray-100 border-b border-gray-200"
                >
                  <td class="px-4 py-3">{{ message }}</td>
                  <td class="px-4 py-3"></td>
                  <td class="px-4 py-3"></td>
                  <td class="px-4 py-3"></td>
                </tr>
              </table>
            </div>
          </div>
        </div>
        <div class="lg:w-2/3 w-2/3 mt-4 lg:mt-2 pl-4 ml-4">
          <a>Conteudo do gráfico...</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
};
</script>