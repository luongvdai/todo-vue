<template>
  <div id="Footer">
    <form action="#" v-on:submit.prevent="addNewItem">
      <input
        v-model="item"
        type="text"
        class="form-control mx-2"
        placeholder="Nhập công việc"
        required
      />
      <button class="btn btn-primary mx-2" type="submit">Thêm</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "todo-footer",
  data() {
    return {
      item: "",
    };
  },
  props: {},
  methods: {
    addNewItem() {
      this.$emit("add-event", this.item);
      this.item = "";
    },
  },
  components: {},
};
</script>

<style>
#Footer > form {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 3%;
}
</style>
