<template>
  <div id="Main" class="d-flex flex-column gap-2 py-2 px-4">
    <todo-item
      v-for="item in listTodo"
      v-bind:key="item.id"
      v-bind:item="item"
      @remove-event="handleDelete(item)"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  name: "todo-main",
  data() {
    return {};
  },
  props: {
    listTodo: {
      type: Array,
      required: true,
    },
  },
  components: {
    TodoItem,
  },
  methods: {
    handleDelete(data) {
      this.$emit("remove-event", data);
    },
  },
};
</script>

<style>
#Main {
  border-bottom: 1px solid black;
  border-top: 1px solid black;
  scroll-behavior: smooth;
  min-height: 70vh;
  max-height: 70vh;
  overflow: auto;
}
</style>
