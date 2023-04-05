<script setup>
import { ref, computed } from 'vue'
import { useQuasar } from 'quasar'

const $q = useQuasar()
const darkMode = ref(false)

const darkModeIcon = computed(() =>
  darkMode.value ? 'light_mode' : 'dark_mode'
)
const showingTooltip = ref(true)
const toggleDarkMode = () => {
  $q.dark.toggle()
  darkMode.value = !darkMode.value
}

</script>

<template>

  <q-btn
    color="accent"
    flat
    round
    dense
    :icon= darkModeIcon
    @click="toggleDarkMode()"
    >
    <q-tooltip v-model="showingTooltip" :delay="1000" anchor="bottom left" > {{darkMode ? "Mode Clair": "Mode Sombre"}} </q-tooltip>

  </q-btn>

</template>

<!-- <style lang="scss">

body.body--light{
  --q-primary : white;
  --q-secondary : var(--nord7);
  --q-accent: var(--nord11)
}

body.body--dark{
  --q-primary : var(--nord1);
  --q-secondary : var(--nord2);
  --q-dark : var(--nord1);
  --q-dark-page : var(--nord1);
  --q-accent: var(--nord9)

}

</style>
 -->
