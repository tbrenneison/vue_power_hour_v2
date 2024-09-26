<template>

  <h1>About My Dumb <span class="strikethrough">Cats</span> Pets</h1>

  <cat-cards/>

</template>

<script setup>
import CatCards from '@/components/catCard.vue'
</script>

<style>
.strikethrough { 
  text-decoration: line-through;
}
</style>
