<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <teleport to=".modal-content">
      <div v-if="showModal" class="modal">
        <h1>This is a modal</h1>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptatibus
          aspernatur officia quia. Recusandae nisi vero autem aspernatur ex
          animi consequuntur deserunt quisquam quos, architecto enim illum omnis
          inventore quis impedit?
        </p>
        <button @click="showModal = false">Hide modal</button>
      </div>
    </teleport>
  </div>
</template>

<script setup>
/*
  imports
*/
import { ref } from "vue";

/*
  modals
*/

const showModal = ref(false);
</script>

<style scoped>
.modal {
  background: beige;
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
</style>
