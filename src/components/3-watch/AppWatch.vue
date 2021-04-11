<template>
    <div class="content-container">
        <sub class="component-title">Watch:</sub>
        <form>
            <label for="name">Nome:</label>
            <input
                id="name"
                type="text"
                v-model="user.nome"
            />
        </form>
        <div>
            <h2>{{ user.nome }}</h2>
            <p>Quantidade de alterações: {{ quantidadeAlteracoes }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppWatch',

    data() {
        return {
            user: {
                nome: 'Matheus Alves Pereira',
                time: 'DEV - ATD',
                dataNascimento: '20/04/1996',
            },

            quantidadeAlteracoes: 0,
        }
    },

    watch: {
        //watch de um propriedade especifica do objeto 'user'
        'user.nome': function () {
            this.quantidadeAlteracoes++;
        },

        //watch da propriedade 'quantidadeAlteracoes' em data
        quantidadeAlteracoes(novaQuantidade, antigaQuantidade) {
            console.log(`quantidadeAlteracoes - Novo === ${novaQuantidade}   ||   Antigo === ${antigaQuantidade}`);
        },


        //watch de todas propriedades do objeto 'user'
        user: {
            handler: function () {
                console.log('<< Atributo do _User_ foi alterado! >>');
            },
            deep: true,
        },

    },

}
</script>

<style lang="scss" scoped>
input {
    margin-left: 10px;
}
</style>
