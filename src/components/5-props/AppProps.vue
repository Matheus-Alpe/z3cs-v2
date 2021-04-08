<template>
    <div class="content-container">
        <sub class="component-title">Props:</sub>
        <UserApp />
        <UserApp v-bind:customPropUser="user" />
        <UserApp :customPropUser="user"></UserApp>
    </div>
</template>

<script>
import UserApp from './components/UserProp'

export default {
    name: 'AppData',

    components: {
        UserApp,
    },

    data() {
        return {
            user: {
                nome: 'Matheus Alves Pereira',
                time: 'DEV - ATD',
                dataNascimento: '20/04/1996'
            }
        }
    }
}
</script>
