<template>
    <div id="counter">
        <button @click="NumberIncrement">+</button><input type="number" :value="count" :min="min" :max="max"><button @click="NumberDecrement">-</button>
    </div>
</template>

<script>
export default {
    name: 'HwCounter',
    data() {
        return {
            min: 1,
            max: 10,
            count: 1
        }
    },
    methods: {
        NumberCounter(event) {
            this.value = event.target.value
            if (this.value >= 10) {
                this.value = 9
            }
        },
        NumberIncrement() {
            if (this.count < this.max) {
                this.count++;
            }
        },
        NumberDecrement() {
             if (this.count > this.min) {
                this.count--;
            }
        },
    }
}
</script>

<style scoped>
#counter {
    margin-left: 550px;
}
</style>