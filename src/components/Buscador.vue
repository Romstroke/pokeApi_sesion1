<template>
    <div>
        <h1>Buscador</h1>
        <form action="">
            <label for="">Id o Nombre:</label>
            <input v-model="ingreso" placeholder="escriba un pokemon">
            <button @click.prevent="buscarPokemon">Buscar</button>
        </form>
   </div>
</template>

<script>
export default {
    name: 'buscador-comp',
    // props: {},
    data: function(){
        return {
            ingreso:'pikachu',
        }
    },
    // computed: {},
    methods: {
        buscarPokemon(){
            if(this.ingreso ==''){
                alert('nombre vacio')
                return
            }
            this.$emit('buscarPokemon',this.ingreso)
        }
    }
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
        button{
            background: #28a645;
            color:#f7f7f7;
            border: none;
            padding: 10px 15px;
        }
        form{
            display:flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            height: fit-content;
        }

</style>