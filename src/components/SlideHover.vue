<template>
  <v-btn flat>
    slide hover
    <v-dialog v-model="dialog" activator="parent">
      <v-card>
        <h4>Hover Me</h4>
        <v-card-actions>
          <v-btn color="primary" block @click="dialog = false">Close</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-btn>
</template>

<script setup lang="ts">
import { ref } from "vue";

const dialog = ref(false);
</script>

<style scoped>
h4::before {
  transform: scaleX(0);
  transform-origin: bottom right;
}

h4:hover::before {
  transform: scaleX(1);
  transform-origin: bottom left;
}

h4::before {
  content: " ";
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  inset: 0 0 0 0;
  background: hsl(200 100% 80%);
  z-index: -1;
  transition: transform 0.3s ease;
}

h4 {
  position: relative;
  font-size: 5rem;
}
</style>
