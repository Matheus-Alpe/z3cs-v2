<template>
    <div class="content-container">
        <sub class="component-title">Computed:</sub>
        <h2>{{ primeiroNome }} tem {{ pegaIdade }} anos!</h2>
    </div>
</template>

<script>
export default {
    name: 'AppComputed',

    data() {
        return {
            user: {
                nome: 'Matheus Alves Pereira',
                time: 'DEV - ATD',
                dataNascimento: '20/04/1996'
            }
        }
    },

    computed: {
        primeiroNome() {
            return this.user.nome.split(' ')[0];
        },

        pegaIdade() {
            const dataLista = this.user.dataNascimento.split('/');
            const idade = new Date().getFullYear() - Number(dataLista[2]);
            return idade;
        },
    }
}
</script>
