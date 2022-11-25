<script setup lang="ts">
  import { Gender, Popularity, Length } from '@/data'

  interface OptionProps {
    option: {
      title: string
      category: string
      buttons: Gender[] | Popularity[] | Length[]
    }
    options: {
      gender: Gender
      popularity: Popularity
      length: Length
    }
  }

  const props = defineProps<OptionProps>()

  const computeButtonClass = (value, index) => {
    console.log(value, index)
    const classNames = []
    if (props.options[props.option.category] === value) {
      classNames.push('option-active')
    }
    if (index === 0) classNames.push('option-left')
    if (index === props.option.buttons.length - 1) {
      classNames.push('option-right')
    }
    return classNames.join(' ')
  }
</script>

<template>
  <div class="options-container">
    <div class="option-container">
      <h4>{{ option.title }}</h4>
      <div class="option-buttons">
        <button
          v-for="(value, index) in option.buttons"
          :key="value"
          class="option"
          :class="computeButtonClass(value, index)"
          @click="options[option.category] = value"
        >
          {{ value }}
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .option-container {
    margin-bottom: 2rem;
  }

  .option {
    background: #fff;
    outline: 0.15rem solid rgb(231, 79, 79);
    border: none;
    width: 12rem;
    padding: 0.75rem;
    color: rgb(27, 60, 138);
    font-weight: 200;
    cursor: pointer;
    transition: 0.7s ease;
  }

  /** top left | top right | bottom right | bottom left*/
  .option-left {
    border-radius: 1rem 0 0 1rem;
  }

  .option-right {
    border-radius: 0rem 1rem 1rem 0rem;
  }

  .option-active {
    background-color: rgb(231, 79, 79);
  }

  
</style>
