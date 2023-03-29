<template>
    <button @click="onClick()" :style="{background: color}" class="btn">{{ text }}</button>
</template>

<script>
import { stringifyExpression } from '@vue/compiler-core';

export default {
    name: 'Button',
    props: {
        text: String,
        color: String,
    },
    methods: {
        onClick(){
            console.log('click')
        }
    }
}
</script>

<style>

</style>