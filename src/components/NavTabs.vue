<template>
  <ul class="nav nav-pills d-flex justify-content-center align-items-center">
    <li v-for="tab in tabs" :key="tab.id" class="nav-item ml-3" style="color:azure">
      <router-link class="nav-link" :to="tab.path">
        <h5>{{tab.title}}</h5>
      </router-link>
    </li>
  </ul>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      tabs: [
        {
          id: uuidv4(),
          title: "Home",
          path: "/home",
        },
        {
          id: uuidv4(),
          title: "About us",
          path: "/home/about",
        },
        {
          id: uuidv4(),
          title: "Teachers",
          path: "/users/teachers",
        },
        {
          id: uuidv4(),
          title: "Q & A",
          path: "/home/qa",
        },
      ],
    };
  },
};
</script>