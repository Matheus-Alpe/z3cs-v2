<template>
    <div class="content-container">
        <sub class="component-title">Props:</sub>
        <user-app :propUser="user" />
        <user-app />
        <user-app v-bind:propUser="user"></user-app>
        <UserApp :propUser="user" />
        <UserApp v-bind:propUser="user"></UserApp>
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
