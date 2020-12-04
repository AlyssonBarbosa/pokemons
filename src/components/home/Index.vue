<template>
    <v-container grid-list-xs>
        <v-row>
            <v-col md="4" sm="12" v-for="pokemon in pokemons.results" :key="'pokemon' + pokemon.name">
                <v-card>
                    <v-card-title primary-title>
                        {{ pokemon }}
                    </v-card-title>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
const axios = require('axios');

export default {
    data () {
        return {
            url:process.env.VUE_APP_URL,
            pokemons: {
                next:null,
                previous: null,
                total: 0,
                results: [],
            },
        };
    },

    created() {
        this.getPokemons(); 
    },

    methods: {
        paginate: function(response) {
            let data = response.data;  
            this.pokemons.next = data.next;
            this.pokemons.previous = data.previous;
            this.pokemons.total = data.count;
            this.pokemons.results = data.results;          
            console.log(response)
        },

        getPokemons: function() {
            let self = this;
            axios.get(`${this.url}pokemon`).then(function(response) {
                self.paginate(response);
            }).catch();
        }
    }
}
</script>

<style>

</style>