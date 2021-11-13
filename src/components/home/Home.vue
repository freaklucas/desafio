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
              v-model="people.name"
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
              v-model="people.lastName"
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
              v-model="people.participation"
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
              @click.prevent="savePeople(people)"
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
                  <th class="px-4 py-3">First name</th>
                  <th class="px-4 py-3">Last name</th>
                  <th class="px-4 py-3">Participation</th>
                </tr>
                <tr
                  v-for="(people, idx) in peoples"
                  :key="idx"
                  class="bg-gray-100 border-b border-gray-200"
                >
                  <td class="px-6 py-4 unique mr-6">
                    {{ idx }}.{{ people.name }}
                  </td>
                  <td class="px-6 py-4">{{ people.lastName }}</td>
                  <td class="px-6 py-4">{{ people.participation }}</td>
                </tr>
              </table>
            </div>
          </div>
        </div>
        <div
          class="lg:w-2/3 w-2/3 mt-4 lg:mt-2 pl-4 ml-4"
          v-for="(people, idx) in peoples"
          :key="idx"
        >
          <pie-chart
            class=""
            :data="[
              [this.people.name, this.people.participation],
              ['João', 23],
            ]"
          ></pie-chart>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      peoples: [],
      people: {
        name: "",
        lastName: "",
        participation: "",
      },
    };
  },
  created() {
    this.peoples = JSON.parse(localStorage.getItem("listsPeople"));
  },
  methods: {
    savePeople(people) {
      let peoples = localStorage.getItem("listsPeople");
      if (peoples) {
        peoples = JSON.parse(peoples);
        peoples.push(people);
      } else {
        peoples = [people];
      }
      this.peoples = peoples;
      localStorage.setItem("listsPeople", JSON.stringify(peoples));
    },
  },
};
</script>