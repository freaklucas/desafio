<template>
  <div class="flex">
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
                <tr class="bg-gray-100 border-b border-gray-200">
                  <td class="px-4 py-3">{{ text }}</td>
                  <td class="px-4 py-3">oi</td>
                  <td class="px-4 py-3">oi</td>
                  <td class="px-4 py-3">10%</td>
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
import Bus from "../bus";

export default {
  name: "Content",
  data: () => ({
    text: "",
  }),
  mounted() {
    Bus.$on("send:message", (value) => (this.text = value));
  },
};
</script>