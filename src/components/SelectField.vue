<script setup lang="ts">
import { SelectFieldProps } from '@/types/propTypes';
import InputWrapper from './InputWrapper.vue';

defineProps<SelectFieldProps>();
</script>

<template>
    <InputWrapper>
        <label :for="id" class="block mb-4 text-xl">
            {{ labelName }}
        </label>
        <select :id="id" :="attributes" :value="value" @change="onInput" class="w-full h-14 outline-none p-2 cursor-pointer bg-primary border-tertiary border-2 rounded text-tertiary transition delay-150 ease-linear
           focus:border-ocean-green" :class="classname" required>
            <option v-for="item in optionList" :value="item">{{ item }}</option>
        </select>
    </InputWrapper>
</template>