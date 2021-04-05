<template>
    <div class="content-container">
        <sub class="component-title">Emits:</sub>
        <UserInput @add-user="pushUser" />


        <UserApp
            v-for="(user, index) in users"
            :key="index"
            :propUser="user"
        />
    </div>
</template>

<script>
import UserInput from './components/UserInput.vue'
import UserApp from './components/UserProp.vue'

export default {
    name: 'AppEmits',

    components: {
        UserInput,
        UserApp,
    },

    data() {
        return {
            users: []
        }
    },

    methods: {
        pushUser(user) {
            this.users.push(user);
        },
    }
}
</script>
