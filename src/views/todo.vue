<template>
  <v-container>
    <ray bansai="Assignment" />
    <v-select v-model="subject" :items="items" label="Subject" solo></v-select>
    <v-col cols="12" sm="6" md="3">
      <v-text-field
        v-model="namestu"
        label="name assignnment"
        solo
      ></v-text-field>
    </v-col>

    <v-textarea
      v-model="lastname"
      clearable
      clear-icon="mdi-close-circle"
      label="detail"
    ></v-textarea>
    <v-btn @click="addTodo" class="mx-2" fab dark color="indigo">
      <v-icon dark> mdi-plus </v-icon>
    </v-btn>
    <v-list dense>
      <v-list-item-group v-model="selectedItem" color="primary">
        <v-list-item v-for="(item, i) in additems" :key="i">
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
          <v-btn
            class="mx-2"
            fab
            dark
            small
            color="error"
            @click="deleteTodo(i)"
          >
            <v-icon dark> mdi-minus </v-icon>
          </v-btn>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-container>
</template>

<script>
import ray from "../components/ray.vue";
export default {
  data() {
    return {
      subject: "",
      namestu: "",
      lastname: "",
      cs: "",
      cs2: "",
      idstu: "",
      items: ["cs313", "cs231", "cs232", "ct301"],
      selectedItem: 1,
      additems: [],
    };
  },
  components: {
    ray,
  },

  methods: {
    addTodo() {
      //console.log(this.subject + this.work);
      this.additems.push({
        text:
          this.subject +
          " " +
          this.namestu +
          " " +
          this.lastname +
          " " +
          this.idstu +
          " " +
          this.cs +
          " " +
          this.cs2,
      });
    },
    deleteTodo(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style></style>
