<template>
  <dialog open>
    <slot></slot>
  </dialog>
</template>

<style scoped>
dialog {
  position: fixed;
  left: 100px;
  top: 100px;
  width: 40%;
  padding: 20px;
  box-shadow: 0 2px 8px grey;
  background-color: white;
}
</style>