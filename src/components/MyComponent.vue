<template>
    <div id="root">
        <label for="">
            Email: 
            <input type="email" :value="email" @input="emailInput">
        </label>
        <label for="">
            Password: 
            <input type="password" :value="password">
        </label>
    </div>
</template>

<script>
export default {
    name: 'MyComponent',
    data() {
        return {
            email: 'example@mail.ru',
            password: '123456789'
        }
    },
    methods: {
        emailInput(event) {
            this.email = event.target.value
        }
    }
}
</script>