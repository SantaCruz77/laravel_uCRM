<script setup>
import Show from '@/Pages/Inertia/Show.vue';
import { computed } from 'vue';

const props = defineProps({
    errors: Object
})
// Show.vueを追加時にconst hasErrors = computed(() => あたりでUncaught TypeError：が発生した
// →なぜか解決した
// const hasErrors = computed(() => Object.keys(props.errors).length > 0);
</script>

<template>
    <div v-if="hasErrors">
        <div class="font-medium text-red-600">問題が発生しました。</div>

        <ul class="mt-3 list-disc list-inside text-sm text-red-600">
            <li v-for="(error, key) in props.errors" :key="key">{{ error }}</li>
        </ul>
    </div>
</template>