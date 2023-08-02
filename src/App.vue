<template>
  <TheHeader />
  <TheMain v-bind:listTodo="listTodo" @remove-event="handleDeleteEvent" />
  <TheFooter @add-event="handleAddEvent" />
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
import TheMain from "./components/layout/TheMain.vue";
import TheFooter from "./components/layout/TheFooter.vue";
export default {
  name: "app",
  data() {
    return {
      listTodo: [
        { id: 0, title: "Do something", active: true },
        { id: 1, title: "Do something", active: false },
        { id: 2, title: "Do something", active: true },
        { id: 3, title: "Do something", active: false },
      ],
    };
  },
  watch: {},
  components: {
    TheHeader,
    TheMain,
    TheFooter,
  },
  computed: {},
  methods: {
    handleAddEvent(data) {
      this.listTodo.push({
        id: this.listTodo.length + 1,
        title: data,
        active: false,
      });
    },
    handleDeleteEvent(data) {
      this.listTodo = this.listTodo.filter((item) => {
        return item.id != data.id;
      });
    },
  },
};
</script>

<style></style>
