<template>
  <div>
    <the-header></the-header>
    <!-- <badge-list></badge-list> -->
    <!-- <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info> -->
    <!-- <course-goals #default="getProps">
      <h2>{{ getProps.item }}</h2>
      <p>{{ getProps["anotherProp"] }}</p>
    </course-goals> -->
    <button @click="selectComponentFunction('active-goals')">
      Active Goals
    </button>
    <button @click="selectComponentFunction('manage-goals')">
      Manage Goals
    </button>
    <!-- <active-goals v-if="selectComponentValue === 'active-goals'"></active-goals>
    <manage-goals v-if="selectComponentValue === 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectComponentValue"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
// import BadgeList from "./components/BadgeList.vue";
// import UserInfo from "./components/UserInfo.vue";
// import CourseGoals from "./components/CourseGoals.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
import ManageGoals from "./components/ManageGoals.vue";

export default {
  components: {
    // UserInfo,
    TheHeader,
    // BadgeList,
    // CourseGoals,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectComponentValue: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    selectComponentFunction(cmp) {
      this.selectComponentValue = cmp;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>