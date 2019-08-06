<template>
    <div id="busqueda">
        Busqueda
        <form v-on:submit="formSubmit">
            <input type="text" v-model="buscarmercado" placeholder="Escriba su busqueda...">
            <input type="submit" value="Search">
        </form>
    </div>
</template>

<script>
export default {
    name: 'busqueda',
    data(){
        return{
            buscarmercado:''
        }
    },
    methods:{
        formSubmit(e){
            this.$emit('formSubmit', this.buscarmercado);
            e.preventDefault();
            
        }
    } 
}
</script>

<style>

</style>
