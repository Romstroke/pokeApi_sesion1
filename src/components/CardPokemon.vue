<template>
    <div>
        <h1>Descripción</h1>
        <div>
            <img :src="img" alt="" srcset="">
            <h2>Id: {{pokemon.id}}</h2>
            <h2>Nombre: {{pokemon.name}}</h2>
            <p>Movimientos: {{moves}}.</p>
            <p>Habilidades: {{abilities}}.</p>
        </div>

    </div>
</template>

<script>
export default {
    name: 'cardPokemon-com',
     props: {
        pokemon:{
            type: Object,
            required:true
        }
     },
    data: function(){
        return {}
    },
     computed: {
        moves(){
          return this.pokemon.moves.map(move=>{
            console.log(move.name)
            return move.move.name
           }).join(', ');
        },
        abilities(){
            return this.pokemon.abilities.map(ability=>{
                return ability.ability.name
            }).join(', ');
        },
        img(){
            return this.pokemon.sprites.front_default
        }
     },
    //methods: {}
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    h1{
        background: #f7f7f7 ;
        border-bottom: 1px solid black;
        margin: 0;
        padding: 10px;
    }
    /* p{
        max-lines: '3'; 
    } */
    
</style>