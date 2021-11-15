<template>
  <div class="testing-comms">
    <h1>Testing Mini App -> Host App Comms thru JS interface</h1>
    <SomeScripts />
  </div>
</template>

<script>
import SomeScripts from '@/components/MoreScripts.vue'

export default {
  name: 'TestingComms',
  components: {
    SomeScripts
  }
}
</script>
