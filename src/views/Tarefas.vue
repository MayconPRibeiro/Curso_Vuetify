<template>
  <div class="home">
    <v-list flat subheader>
      <v-col cols="12" sm="6">
        <v-text-field
          v-model="campoInput"
          label="Digite uma nova tarefa"
          clearable
          @keyup.enter="handleAddTarefa"
        ></v-text-field>
      </v-col>

      <v-subheader>Todas as tarefas</v-subheader>

      <v-list-item-group multiple active-class="">
        <div v-for="(tarefa, index) in tarefas" :key="index">
          <Tarefa :tarefa="tarefa" />
        </div>
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
  data() {
    return {
      campoInput: null,
      tarefas: [
        { titulo: "Ir ao mercado", concluido: false },
        { titulo: "Comprar ração", concluido: false },
      ],
    };
  },
  methods: {
    handleAddTarefa() {
      if (this.campoInput) {
        this.tarefas.push({
          titulo: this.campoInput,
          consluido: false,
        });
        this.campoInput = null;
      }
    },
  },
};
</script>
