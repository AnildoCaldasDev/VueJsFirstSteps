<template>
  <b-container class="mt-3">
    <b-row align-v="center">
      <card v-for="curso in cursos" :key="curso.id" :nome="curso.nome"></card>
    </b-row>
  </b-container>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";

export default {
  name: "Home",
  data() {
    return {
      cursos: [],
    };
  },
  components: {
    Card,
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const res = await fetch("cursos.json");
      const val = await res.json();
      this.cursos = val;
    },
  },
};
</script>
