<template>
  <div class="container">
    <global-header :user="user"></global-header>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import "bootstrap/dist/css/bootstrap.min.css";
import ColumnList, { ColumnProps } from "@/components/ColumnList.vue";
import GlobalHeader, { UserProps } from "@/components/GlobalHeader.vue";
const userData: UserProps = { name: "陈威", isLogin: true, id: 0 };
const testData: ColumnProps[] = [
  {
    id: 1,
    title: "test1",
    description: "description",
    avatar: require("@/assets/地球.png")
  },
  {
    id: 2,
    title: "test2",
    description: "description",
    avatar: require("@/assets/地球.png")
  },
  {
    id: 3,
    title: "test2",
    description: "description"
    // avatar: "../assets/logo.png"
  },
  {
    id: 4,
    title: "test2",
    description: "description",
    avatar: require("@/assets/地球.png")
  }
];
export default defineComponent({
  name: "App",
  components: {
    ColumnList,
    GlobalHeader
  },
  setup() {
    return {
      list: testData,
      user: userData
    };
  }
});
</script>

<style></style>
