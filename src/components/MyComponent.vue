<template>
    <div id="root">
        <label for="">
            Email: 
            <input type="email" :value="email" @input="emailInput">
        </label> <br> <br>

        <label for="">
            Password: 
            <input type="password" :value="password" @input="passInput">
        </label><br> <br>

        Email: {{ email }}
        Password: {{ password }}
    </div>
</template>

<script>
export default {
    name: 'MyComponent',
    data() {
        return {
            email: 'example@mail.ru',
            password: '123456789',
        }
    },
    methods: {
        emailInput(event) {
            this.email = event.target.value
        },
        passInput(event) {
            this.password = event.target.value
        },
        
    },
}
</script>