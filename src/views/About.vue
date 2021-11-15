<template>
  <div class="about">
    <h1>This is an about page</h1>
    <SomeScripts />
  </div>
</template>

<script>
import SomeScripts from '@/components/SomeScripts.vue'

export default {
  name: 'About',
  components: {
    SomeScripts
  }
}
</script>
