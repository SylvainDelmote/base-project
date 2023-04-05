<script setup>

const props = defineProps({
  title: {
    type: String,
    required: true,
    default: 'Brand'
  },
  mobile: {
    type: Boolean,
    default: false
  },
  image: {
    type: String,
    default: 'https://cdn.quasar.dev/img/boy-avatar.png'
  },
  lien: {
    type: String,
    default: '/'
  }

})

</script>

<template>
<RouterLink to="/">
  <div  v-if="!props.mobile" class="absolute-top" style="height: 100px">
    <div class="absolute-bottom bg-transparent q-pa-md flex items-center q-gutter-lg">
      <q-avatar size="56px" class="q-mb-sm" >
        <img :src="props.image">
      </q-avatar>
      <div class="text-h6">{{props.title}} </div>
    </div>
  </div>
  <div v-else  class="absolute-top">
    <q-avatar size="40px" class="q-ma-sm">
      <img :src="props.image">
      <q-tooltip> {{props.title}}</q-tooltip>
    </q-avatar>
  </div>
</RouterLink>

</template>
