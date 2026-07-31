<template>
  <div>
    <v-list-item>
      <template v-slot:default="{ active }">
        <v-list-item-action>
          <v-checkbox :input-value="active"></v-checkbox>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title>{{ tarefa.titulo }}</v-list-item-title>
        </v-list-item-content>

        <v-list-item-action>
          <v-btn icon @click.stop="handleRemoveTarefa(tarefa.id)">
            <v-icon color="red">mdi-delete</v-icon>
          </v-btn>
        </v-list-item-action>
      </template>
    </v-list-item>
    <v-divider></v-divider>
  </div>
</template>

<script>
export default {
  props: ["tarefa"],
  methods: {
    handleRemoveTarefa(id) {
      this.$store.commit("removeTarefa", id);
    },
  },
};
</script>

<style></style>
