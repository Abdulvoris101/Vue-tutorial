<template>
    <div id="root">
        {{ text }}
    </div>
</template>

<script>
export default {
    name: 'MyComponent',
    data() {
        return {
            text: 'Hello'
        }
    }
}
</script>