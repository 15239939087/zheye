<template>
  <nav
    class="navbar navbar-dark bg-primary justify-content-between mb-4 pr-4 pl-4"
  >
    <a href="#" class="navbar-brand">者也专栏</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="" class="btn btn-outline-light">登录</a>
      </li>
      <li class="list-inline-item">
        <a href="" class="btn btn-outline-light">注册</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="" class="btn btn-outline-light">你好 {{ user.name }}</a>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";

export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
export default defineComponent({
  name: "HelloWorld",
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  }
});
</script>
