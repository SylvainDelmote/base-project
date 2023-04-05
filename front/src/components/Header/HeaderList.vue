
<script setup>
import EssentialLink from './EssentialLink.vue'
import data from '../../data/array.json'
</script>

<template>
<q-list style= "height: calc(100% - 100px); margin-top: 100px;" >
  <q-item-label header> Essential Links </q-item-label>
  <EssentialLink
    v-for="link in data"
      :key="link.title"
      v-bind="link"
    />
</q-list>

</template>
