<script setup>
import { ref, computed } from 'vue'
import { useQuasar } from 'quasar'
import DarkModeButton from 'components/Buttons/DarkmodeButton.vue'
import HeaderLogo from 'src/components/Header/HeaderLogo.vue'
import HeaderList from 'src/components/Header/HeaderList.vue'
import logo from '../assets/logo.png'

const $q = useQuasar()
const leftDrawerOpen = ref(true)

const mobile = computed(() => {
  return $q.screen.lt.md
})

</script>

<template>

<q-layout  view="lhh lpR lFf">
    <q-drawer
      behavior = "desktop"
      class = "drawer"
      v-model="leftDrawerOpen"
      bordered
      :mini = mobile
    >

    <HeaderList />
    <HeaderLogo :mobile="mobile" title="Titre" :image=logo />

    </q-drawer>

    <q-header>
      <q-toolbar class="flex justify-end" >
        <DarkModeButton />
      </q-toolbar>

    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>

</template>

<style>
.drawer{
  background-image: url('../assets/background.svg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: left;

}
</style>
