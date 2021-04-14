<template>
    <div class="content-container">
        <sub class="component-title">Component: UserInput</sub>
        <form>
            <div class="input-field">
                <label for="nome">Nome:</label>
                <input type="text" id="nome" v-model="user.nome">
            </div>
            <div class="input-field">
                <label for="time">Time:</label>
                <input type="text" id="time" v-model="user.time">
            </div>
            <div class="input-field">
                <label for="dataNasc">Data Nascimento:</label>
                <input type="date" id="dataNasc" v-model="user.dataNascimento">


                <div class="button-field">
                    <button class="reset" @click.prevent="resetUser">Reset</button>
                    <button class="add" @click.prevent="emitAddUser">Add User</button>
                </div>


            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'UserInput',

    data() {
        return {
            user: {
                nome: '',
                time: '',
                dataNascimento: ''
            }
        }
    },

    methods: {


        emitAddUser() {
            if (!this.user.nome || !this.user.time || !this.user.dataNascimento) {
                return;
            }

            const user = {
                ...this.user,
                dataNascimento: this.normalizeDataNasc()
            }

            console.log('emitiu o evento "add-user"')


            //============================
            this.$emit('add-user', user);
            //============================


            this.resetUser();
        },






        resetUser() {
            this.user.nome = '';
            this.user.time = '';
            this.user.dataNascimento = '';
        },

        normalizeDataNasc() {
            return this.user.dataNascimento.split('-').reverse().join('/');
        }
    }
}
</script>

<style lang="scss" scoped>
form {
    margin: 30px auto 0;
    max-width: 80%;

    .input-field {
        margin: 15px auto 0;

        label {
            float: left;
            margin-right: 10px;
        }

        input {
            display: block;
            height: 20px;
        }

        input[type="text"] {
            width: 100%;
        }

        .button-field {
            margin: 10px auto 0;
            display: flex;
            justify-content: space-between;
        }
    }
}
</style>
