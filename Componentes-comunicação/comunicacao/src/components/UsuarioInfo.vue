<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        <p>Nome do usuário: <strong>{{ inverterNome() }}</strong> </p>
        <p>Idade do usuário: {{idade}} anos</p>
        <button @click="reiniciarNome()">Reiniciar nome</button>
        <button @click="reiniciarFN()">Reiniciar nome (callback)</button>
    </div>
</template>

<script>

export default {
    props: {
        nome: {
            type: String,
            require: true
            //default: "Anônimo"
        },
        reiniciarFN: {
            type: Function,
        },
        idade: {
            type: Number
        }
    },
    methods: {
        inverterNome(){
            return this.nome.split('').reverse().join('')
        },
        reiniciarNome(){
            const antigo = this.nome
            this.nome = 'pedro'
            this.$emit("nomeMudou", {
                novo: this.nome,
                antigo
            })
        }
    }
}
</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #ec485f;
        color: #fff;
    }
</style>
