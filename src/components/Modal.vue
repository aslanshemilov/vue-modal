<template>
  <div class="modal-container" :class="{ 'modal-container--show' : open}">
    <div class="modal-body">
      <span @click="closeModal()" class="modal-close">&times;</span>
      <slot name="body"></slot>
    </div>
    <div class="modal-backdrop"></div>
  </div>
</template>

<script>
export default {
  props: ["open"],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
.modal-container {
  display: none;
}
.modal-container--show {
  display: flex;
  position: absolute;
  top: 25%;
  left: 25%;  
}
.modal-body {
  z-index: 99;
  width: 500px;
  height: 300px;
  background: #fff;
  border: 1px solid black;
}
.modal-backdrop {
  z-index: 66;
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgba(0, 0,0, 0.3);
}
.modal-close {
  font-size: 42px;
  float: right;
  cursor: pointer;
  margin-right: 10px;
}
</style>


