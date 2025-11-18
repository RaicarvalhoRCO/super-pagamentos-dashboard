<template>
    <svg width="48" height="16" viewBox="0 0 48 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path :d="path" :stroke="color" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
    </svg>
</template>

<script>
export default {
    name: 'IconSparkline',
    props: {
        path: {
            type: String,
            required: true
        },
        color: {
            type: String,
            default: '#9D5CFF'
        }
    }
}
</script>
