<template>
  <div class="p-4 border-t border-gray-100 flex">
    <div v-if="!showMenu">
      <BaseTextButton @click="toogleMenu" class="mr-2" color="indigo"
        >Move</BaseTextButton
      >

      <BaseTextButton @click="taskRemoved" style="" clas="" color="red">
        Delete
      </BaseTextButton>
    </div>

    <TodoListItemMenuMove v-else @closed="toogleMenu" />
  </div>
</template>

<script setup>
import BaseTextButton from "./../base/BaseTextButton.vue";
import TodoListItemMenuMove from "./TodoListItemMenuMove.vue";
// import { REMOVE_TASK } from "./../../store/mutation-types";
// import { mapMutations } from "vuex";

import { ref, inject } from "vue";
const showMenu = ref(false);
const toogleMenu = () => (showMenu.value = !showMenu.value);
const task = inject("task");
const projectId = inject("projectId");
const taskRemoved = () =>
  console.log(`it's not implemented yet, ${task.id} and ${projectId}`);
</script>
