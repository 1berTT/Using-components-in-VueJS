<template>
    <div class="componente">
        <h2>Alterar os Dados de Usuário</h2>
        <p>Idade do usuario: {{idade}} anos</p>
        <p>Edite as informações</p>
        <button @click="alterarIdade()">Alterar idade</button>
    </div>
</template>

<script>


export default {
    props: {
        idade: {
            type: Number
        }
    },
    methods: {
        alterarIdade(){
            this.idade = 22
            this.$emit('idadeMudou', {
                novo: this.idade
            })
        }
    }
}
</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #98b99a;
        color: #fff;
    }
</style>
