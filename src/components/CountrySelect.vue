<template>
    <select @change="onChange" v-model="selected" class="fofrm-select mt-10 block w-full border p-3 rounded">
        <option value="0">Select Country</option>
        <option v-for="country in countries" :key="country.ID" :value="country.ID"> {{ country.Country }} </option>
    </select>
</template>

<script>
    export default{
        name: 'CoutrySelect',
        props: ['countries'],
        data() {
            return {
                selected: 0
            }
        },
        methods: {
            onChange(){
                const city = this.countries.find((element) => element.ID === this.selected)
                this.$emit('bring-country', city)
            }
        },
    }
</script>