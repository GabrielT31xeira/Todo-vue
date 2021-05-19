<template>
  <div class="flex flex-col mt-3">
    <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
      <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
        <div
          class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg"
        >
          <table class="min-w-full divide-y divide-gray-200">
            <thead class="bg-gray-50">
              <tr>
                <th
                  scope="col"
                  class="px-6 py-3 text-center text-xs font-medium text-gray-500 uppercase tracking-wider"
                >
                  Descrição
                </th>
                <th
                  scope="col"
                  class="px-6 py-3 text-center text-xs font-medium text-gray-500 uppercase tracking-wider"
                >
                  Concluir
                </th>
                <th
                  scope="col"
                  class="px-6 py-3 text-center text-xs font-medium text-gray-500 uppercase tracking-wider"
                >
                  Remover
                </th>
              </tr>
            </thead>
            <tbody class="bg-white divide-y divide-gray-200">
              <tr>
                <td class="px-6 py-4 whitespace-nowrap">
                  <div class="flex items-center">
                    <div class="ml-2">
                      <div
                        class="text-base font-medium text-gray-900"
                        :class="{ checked: todo.checked }"
                      >
                        <i
                          class="icon"
                          :class="todo.checked ? 'icon-check' : 'icon-time'"
                        ></i>
                        {{ todo.description }}
                      </div>
                    </div>
                  </div>
                </td>
                <td class="px-6 py-4 whitespace-nowrap">
                  <button
                    @click="$emit('toggle', todo)"
                    class="ml-3 bg-green-500 hover:bg-green-900 duration-150 delay-75 rounded-md p-0.5 px-2 appearance-none"
                  >
                    <span v-if="todo.checked">Desmarcar</span>
                    <span v-else>Concluido</span>
                  </button>
                </td>
                <td class="px-6 py-4 whitespace-nowrap">
                  <button
                    @click="$emit('remove',todo)"
                    class="ml-3 bg-red-500 hover:bg-red-900 duration-150 delay-75 rounded-md p-0.5 px-2 appearance-none"
                  >
                    Remover
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: { type: Object, required: true },
  },
};
</script>

<style scoped>
.checked {
  text-decoration: line-through;
  color: lightgray;
}
</style>

