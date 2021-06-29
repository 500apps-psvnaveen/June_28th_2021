<template>
  <div>
    <h1>Manage Goals</h1>
    <input type="text" ref="inputValue" />
    <button @click="setGoal">Goal</button>
    <teleport to="body">
      <error-alert v-if="inputCheck">
        <h2>Input feild is empty!</h2>
        <p>Enter Some text into the field and then try.</p>
        <button @click="giveChance">Okay</button>
      </error-alert>
    </teleport>
  </div>
</template>

<script>
import ErrorAlert from "./UI/ErrorAlert.vue";

export default {
  components: {
    ErrorAlert,
  },
  data() {
    return {
      inputCheck: false,
    };
  },
  methods: {
    setGoal() {
      const checkValue = this.$refs.inputValue.value;

      if (checkValue === "") {
        this.inputCheck = true;
      }
    },
    giveChance() {
      this.inputCheck = false;
    },
  },
};
</script>