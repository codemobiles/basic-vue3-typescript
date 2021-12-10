<template>
    <div>
        <h1>App.Vue</h1>
        <span>#Debug: {{count1}}</span>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    setup() {
        return {
            count1: 10
        }    
    },
})
</script>
