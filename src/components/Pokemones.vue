<template>
    <div>
        <h1>pokemones</h1>
        <div class="container">
             <Buscador class="buscador" @buscarPokemon='setNamePokemon'/>
             <CardPokemon class="card" :pokemon="pokemonInfo"/>
        </div>
       
    </div>
</template>

<script>
import Buscador from '@/components/Buscador.vue'
import CardPokemon from '@/components/CardPokemon.vue'

export default {
    name: 'pokemones-com',
    // props: {},
    data: function(){
        return {
            pokemonName:'pikachu',
            pokemonInfo:{
                id:'',
                name:'',
                sprites:'',
                moves:[],
                abilities:[]
            }
        }
    },
    // computed: {},
    methods: {
        setNamePokemon(name){
            //console.log(name)
            this.pokemonName = name;
        },
        getPokemon(){
            fetch(`https://pokeapi.co/api/v2/pokemon/${this.pokemonName}`)
            .then(resp =>resp.json())
            .then(json =>{
                console.log(json)
                this.pokemonInfo.id = json.id
                this.pokemonInfo.name = json.name
                this.pokemonInfo.sprites =json.sprites
                this.pokemonInfo.abilities= json.abilities
                this.pokemonInfo.moves= json.moves
            })
            .catch(error=> console.log(error))
        }
    },
    watch: {
        pokemonName(value){
            if(value != ''){
                this.getPokemon()
                console.log(value)
            }
        }
    },
     components: {
        Buscador,
        CardPokemon
     },
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    created(){
        this.getPokemon()
    }
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .container{
        display:flex;
        width: 70%;
        margin:0 auto;
        gap: 15px;
    }
    .buscador{
        flex-basis: 50%;
        border: 1px solid black;
        align-self:start;
    }
    .card{
        flex-basis: 50%;
        border: 1px solid black;

    }
</style>