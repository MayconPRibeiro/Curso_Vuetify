<template>
  <div class="home">
    <v-list flat subheader>
      <v-subheader>Todas as tarefas</v-subheader>

      <v-list-item-group v-model="settings" multiple active-class="">
        <Tarefa />
        <Tarefa />
        <Tarefa />
      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
import Tarefa from "../components/tarefas/Tarefa.vue";

export default {
  name: "Home",
  components: {
    Tarefa,
  },
};
</script>
