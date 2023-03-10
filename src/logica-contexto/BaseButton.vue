<script setup lang='ts'>
type ButtonColors = 'primary' | 'secondary'

interface Props {
    color: ButtonColors,
    label: string
}
const emit = defineEmits(['action'])

const props = withDefaults(defineProps<Props>(), {
    color: 'secondary',
}) 

const action = () => emit('action')
</script>
    
<template>
    <v-btn
      variant="flat"
      :color="props.color"
      @click="action"
    >
      {{ props.label }}
    </v-btn>
</template>
    
<style lang='postcss' scoped>
    
</style>