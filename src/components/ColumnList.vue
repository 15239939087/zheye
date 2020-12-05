<template>
  <div class="row">
    <div v-for="item in columnList" :key="item.id" class="col-4 mb-3">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
          <img
            :src="item.avatar"
            :alt="item.title"
            class="rounded-circle border border-light w-25 my-3"
          />
          <h5 class="card-title">{{ item.title }}</h5>
          <p class="card-text text-left">{{ item.description }}</p>
          <a href="" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType, computed, reactive } from "vue";
export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
export default defineComponent({
  name: "column-list",
  components: {},
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup(props) {
    const state = reactive({
      name: "帅的没人要",
      sex: "性别分不出",
      arr: [{ isBasic: true }, { isBasic: true }]
    });
    const columnList = computed(() => {
      console.log(state.arr[1]?.isBasic);
      return props.list.map(column => {
        if (!column.avatar) {
          column.avatar = require("@/assets/logo.png");
        }
        return column;
      });
    });
    return { columnList };
  }
});
</script>

<style scoped></style>
