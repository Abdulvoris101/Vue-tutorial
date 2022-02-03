<template>
    <form id="form" class="sign-up" >
        
        <div class="mb-3 mt-3">
            <label for="login">Login: </label>
            <input type="text" v-model.trim="form.login" id="login" class="form-control">
        </div>
        <div class="mb-3">
            <label for="email">Email: </label>
            <input type="text" v-model.trim="form.email" id="email" class="form-control">
        </div>
        
        <div class="mb-3">
            <label for="password">Password: </label>
            <input type="password" v-model.trim="form.password" id="password" class="form-control">
        </div>
        <div class="mb-3">
            <label for="country">Country: </label>
            <select name="" id="country" class="form-control" v-model="form.country">
                <option 
                v-for="(country, index) in countries" 
                :key="index" 
                :value="country.value">
                    {{country.label}}
                </option>
                
            </select>
        </div>
        <div class="mb-3">
            <label for="themes">Favourite themes: </label>
             <select name="" id="themes" class="form-control" v-model="form.favouriteTheme" multiple>
                <option 
                v-for="(theme, index) in themes" 
                :key="index" 
                :value="theme.value">
                    {{ theme.label }}
                </option>
                
            </select>
        </div>
         <div class="mb-3 form-check">
             <input type="checkbox" v-model="form.allowEmailWithSend" id="notification" class="form-check-input">
            <label for="notification" class="form-check-label">Notifications </label>
        </div>
        <div class="d-flex mb-3">
            <div class="form-check me-2">
                <input type="radio" 
                value="male" class="form-check-input" id="male" 
                name="exampleRadio" v-model="form.gendere" checked>
                <label for="male" class="form-check-label">
                    Male
                </label>
            </div>
            <div class="form-check">
                <input type="radio" 
                value="female" class="form-check-input" id="female" 
                name="exampleRadio" v-model="form.gendere">
                <label for="female" class="form-check-label" >
                    Female
                </label>
            </div>
        </div>
        <button type="submit" @click="submitForm" class="btn btn-primary">Save</button>
    </form>
</template>

<script>
import useVuelidate from '@vuelidate/core'
import { required } from '@vuelidate/validators'

export default {
    name: 'SignUp',
    data() {
        return {
            $v: useVuelidate(),
            form: {
                login: '',
                email: '',
                password: '',
                country: 'ru',
                favouriteTheme: ['IT'],
                allowEmailWithSend: false,
                gendere: 'male',
            },
            countries: [
                {
                    label: 'Russian',
                    value: 'ru'
                },
                {
                    label: 'Uzbekistan',
                    value: 'uz'
                },
                {
                    label: 'USA',
                    value: 'usa'
                }
            ],
            themes: [
                {
                    label: 'IT-Texnologic',
                    value: 'IT'
                },
                {
                    label: 'Mathematic',
                    value: 'math'
                },
                {
                    label: 'Languages',
                    value: 'language'
                },

            ],
             
            
        }
    },
    validations () {
        return {
            form: {
                login: {
                    required,
                }
            }
        }
    },
    methods: {
        submitForm() {
            console.log(this.$v);
            alert("Succesfully")
        }
    }
   
   
}
</script>

<style scoped>
#form {
    width: 700px;
    margin-left: auto;
    margin-right: auto;
}
</style>