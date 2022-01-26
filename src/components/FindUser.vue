<template>
    <div id="find">
        Qidirish
        <br><br>
        <input type="text" @input="searchText = $event.target.value">
        <p>Barcha Ismalr: {{ names.length }}, oxshashlik: {{ getFilteredNames.length }}</p>
        <ul class="list">
        <li
            v-for="(name, index) in getFilteredNames"
            :key="index"
        >
            {{ name }}
        </li>
        </ul>
 
    </div>
</template>

<script>
export default {
    name: 'FindUser',
    data() {
        return {
            searchText: '',
            names: ['Abdulvoris', 'Muhammad', 'Abdulloh', 'Abdurrahmon', 'Iskandar']

            
        }
    },
    computed: {
        getFilteredNames() {
            return this.names.filter(name => name.toLowerCase().includes(this.searchText.toLowerCase()))
        }

    }

}
// stable version
</script>

