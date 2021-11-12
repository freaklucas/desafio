<template>
  <div class="">
    <div class="flex">
      <div class="flex-nowrap ml-16">
        <form @submit.prevent="onSubmit" class="w-full center max-w-lg mr-8">
          <div class="flex flex-row -mx-5 mb-6"></div>
        </form>
      </div>
    </div>
    <div class="card-table">
      <div class="flex mb-12">
        <table
          class="roundend-t-sm text-sm w-5/6 mx-auto font-mono text-gray-800"
        >
          <tr class="text-left border-b-2 border-gray-300">
            <th class="px-4 py-3">Código</th>
            <th class="px-4 py-3">Nome</th>
            <th class="px-4 py-3">Caminho</th>
          </tr>
          <tr
            class="bg-gray-100 border-b border-gray-200"
            v-for="list in lists"
            :key="list"
          >
            <td class="px-4 py-3">{{ (counter += 1) }}</td>
            <td class="px-4 py-3">{{ list.name }}</td>
            <td class="px-4 py-3">{{ list.path }}</td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Table",
  data() {
    return {
      lists: [],
      title: "Lista de cadastro",
      list: {
        code: "",
        name: "",
        path: "",
      },
      counter: 0,
    };
  },
  created() {
    this.lists = JSON.parse(localStorage.getItem("listsApp"));
  },
  methods: {
    saveList(list) {
      let lists = localStorage.getItem("listsApp");
      if (lists) {
        lists = JSON.parse(lists);
        lists.push(list);
      } else {
        lists = [list];
      }
      this.lists = lists;
      localStorage.setItem("listsApp", JSON.stringify(lists));
    },
  },
};
</script>