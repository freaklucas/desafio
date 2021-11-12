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
      <div class="flex align-center mt-12">
        <div class="lg:w-2/3 md:w-2/3 mr-8 ml-4 sm:px-6 lg:px-4 center">
          <div class="flex">
            <div class="flex-nowrap ml-16">
              <form
                @submit.prevent="onSubmit"
                class="w-full center max-w-lg mr-8"
              >
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
                  class="bg-gray-100 border-b border-gray-200"
                  v-for="list in lists"
                  :key="list"
                >
                  <td class="px-4 py-3">{{ (counter += 1) }}</td>
                  <td class="px-4 py-3">{{ list.name }}</td>
                  <td class="px-4 py-3">{{ list.path }}</td>
                  <td class="px-4 py-3">{{ list.path }}</td>
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
  name: "Content",
  data() {
    return {
      title: [{ text: "DATA" }],
      description: [
        { text: "Lorem ipsum dolor si amet, consectetur adipiscing elit." },
      ],
      lists: [],
      list: {
        code: "",
        firstName: "",
        lastName: "",
      },
      counter: 0,
    };
  },
  created() {
    this.lists = JSON.parse(localStorage.getItem("listsNames"));
  },
  methods: {
    saveList(list) {
      let lists = localStorage.getItem("listsNames");

      if (lists) {
        lists = JSON.parse(lists);
        lists.push(list);
      } else {
        lists = [list];
        localStorage.setItem("listsNames", JSON.stringify(lists));
      }
    },
  },
};
</script>