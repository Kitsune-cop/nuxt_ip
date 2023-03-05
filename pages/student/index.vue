<template lang="html">
    <div>
        <v-data-table :headers="headers" :items="desserts" item-key="name" class="elevation-1" :search="search"
            :custom-filter="filterOnlyCapsText">
            <template v-slot:top>
                <v-row>
                    <v-col cols="9">
                        <v-text-field v-model="search" label="Search (UPPER CASE ONLY)" class="mx-4"></v-text-field>
                    </v-col>
                    <v-col class="pt-6">
                        <v-btn color="success" rounded class="me-2">Search</v-btn>
                        <v-btn color="primary" rounded><v-icon dark>mdi-plus</v-icon>New Student</v-btn>
                    </v-col>
                </v-row>
            </template>
            <template v-slot:body.append>
                <tr>
                    <td></td>
                    <td>
                        <v-text-field v-model="calories" type="number" label="Less than"></v-text-field>
                    </td>
                    <td colspan="4"></td>
                </tr>
            </template>
        </v-data-table>
    </div>
</template>
<script>
export default {
    layout: 'admin',
    data() {
        return {
            search: '',
            calories: '',
            desserts: [
                {
                    name: 'Frozen Yogurt',
                    calories: 159,
                    fat: 6.0,
                    carbs: 24,
                    protein: 4.0,
                    iron: 1,
                },
                {
                    name: 'Ice cream sandwich',
                    calories: 237,
                    fat: 9.0,
                    carbs: 37,
                    protein: 4.3,
                    iron: 1,
                },
            ]
        }
    },
    computed: {
        headers() {
            return [
                {
                    text: 'Dessert (100g serving)',
                    align: 'start',
                    sortable: false,
                    value: 'name',
                },
                {
                    text: 'Calories',
                    value: 'calories',
                    filter: value => {
                        if (!this.calories) return true

                        return value < parseInt(this.calories)
                    },
                },
                { text: 'Fat (g)', value: 'fat' },
                { text: 'Carbs (g)', value: 'carbs' },
                { text: 'Protein (g)', value: 'protein' },
                { text: 'Iron (%)', value: 'iron' },
            ]
        },
    },
    methods: {
        filterOnlyCapsText(value, search, item) {
            return value != null &&
                search != null &&
                typeof value === 'string' &&
                value.toString().toLocaleUpperCase().indexOf(search) !== -1
        },
    },
}
</script>
<style lang="css"></style>