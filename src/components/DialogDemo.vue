<template>
  <div>Dialog 示例</div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="show" :closeOnClickOverlay="true">
    <template v-slot:title>
      <strong>toggle</strong>
    </template>
    <strong>hi</strong>
    <div>hi2</div>
    <template v-slot:footer>
      <!--      <Button level="main" @click="ok">OK</Button>-->
      <!--      <Button @click="cancel">Cancel</Button>-->
      <Button level="main">OK</Button>
      <Button>Cancel</Button>
    </template>
  </Dialog>
  <h1>示例2</h1>
  <!--  <Button @click="showDialog">show</Button>-->
</template>

<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'
import {
  ref,
  h
} from 'vue'
import {
  openDialog
} from '../lib/openDialog'

export default {
  components: {
    Dialog,
    Button
  },
  setup () {
    const show = ref(false)
    const toggle = () => {
      show.value = !show.value
    }
    return {
      show,
      toggle
      // showDialog
    }
  }
}
</script>
