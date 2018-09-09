<template>
  <div>
    <button @click="open = !open">SHOW MODAL</button>
    <modal @close="open = !open" :open="open">
      <template slot="body">
        <h1>THIS IS THE NEW HEADER FROM THE APP</h1>
      </template>
    </modal>
  </div>
</template>

<script>
import Modal from '@/components/Modal.vue'

export default {
  name: 'app',
  components: {
    Modal
  },
  data: () => ({
    open: false
  })
}
</script>

<style>
button {
  padding: 30px 60px;
}
</style>
