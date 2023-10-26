<template>
    <header>
        <h1>
            <img src="../assets/objetivo.png" alt="Seus Objetivos">
        </h1>
        <h2> Menu Lateral </h2>
    </header>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BarraLateral'
})
</script>
<style scoped>

header {
  background: #0a0a18;
  color: #fbfdff;
  width: 100%;
  height: 100vh;
}

img {
  display: flex;
  height: auto;
  max-width: 25%;
  padding: 1rem 0;
  margin-left: 5rem;
  border-radius: 3rem;
} 

h2 {
  padding: 2em;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>