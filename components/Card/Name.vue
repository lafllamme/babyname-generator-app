<script setup lang="ts">
  interface NameProps {
    name: string
    index: number
  }

  const props = defineProps<NameProps>()

  const emit = defineEmits(['remove'])

  const removeName = () => {
    emit('remove', props.index)
  }

  console.log(props, 'WE ARE HRE')
</script>

<template>
  <div>
    <div class="card">
      <h4>{{ name }}</h4>
      <p @click="removeName()">x</p>
    </div>
  </div>
</template>

<style scoped>
  .card {
    background-color: rgb(27, 60, 138);
    min-width: 4rem;
    color: white;
    border-radius: 1rem;
    padding: 0.3rem;
    margin-right: 0.5rem;
    margin-bottom: 1rem;
    position: relative;
  }
  .card p {
    position: absolute;
    top: -20%;
    left: 80%;
    padding: 0.1rem;
    cursor: pointer;
    color: rgba(244, 244, 244, 1);
  }
</style>
