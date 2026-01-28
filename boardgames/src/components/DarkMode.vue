<script setup>
    const props = defineProps(['colorMode'])
    const emit = defineEmits(['update:colorMode'])

    const toggleTheme = (checked)=>{
        const newMode = checked ? 'dark' : 'light';
        emit('update:colorMode', newMode)
    }
</script>

<template >
    <div class = "background-selection">
    <v-switch 
        density="compact"
        hide-details
        label="Light/Dark"
        :model-value = "colorMode ==='dark'"
        @update:model-value="toggleTheme"
        color= "primary"
        class="compact-switch"
        >
    </v-switch>
    </div>
    
</template>

<style scoped>
/*shrinks the default vutefity box size*/
.compact-switch :deep(.v-selection-control) {
  min-height: 1px; 
}

/* shrinks text size */
.compact-switch :deep(.v-label) {
  font-size: 0.75rem;
  opacity: 2;
}

/*shrinks the toggle switch size */
.compact-switch :deep(.v-switch__track),
.compact-switch :deep(.v-switch__thumb) {
  transform: scale(0.6);
}
</style>