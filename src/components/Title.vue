<script setup lang="ts">
import { TitleProps } from '../types/propTypes';

defineProps<TitleProps>();
</script>

<template>
    <h1
        class="text-5xl font-bold bg-gradient-to-r from-ocean-green to-pickled-bluewood bg-clip-text text-transparent inline-block mb-8 max-[430px]:text-2xl">
        < {{ title }} />
    </h1>
</template>