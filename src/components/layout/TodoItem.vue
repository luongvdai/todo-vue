<template>
  <div
    class="item form-control d-flex justify-content-between align-items-center"
    v-bind:class="{ active: item.active }"
  >
    <h4>{{ item.title }}</h4>
    <div class="option">
      <done-vue v-if="item.active === false" @click="item.active = true" />
      <remove-vue />
    </div>
  </div>
</template>

<script>
import doneVue from "../common/icons/done.vue";
import removeVue from "../common/icons/remove.vue";
export default {
  name: "todoItem",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  components: {
    doneVue,
    removeVue,
  },
  methods: {},
  computed: {},
};
</script>

<style>
.active {
  background: greenyellow;
  transition: 0.4s;
}
</style>
