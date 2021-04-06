<template>
    <div class="content-container">
        <sub class="component-title">Method:</sub>
        <h1>Contador: {{ contador }}</h1>
        <div>
            <button v-on:click="incrementCount">Incrementar</button>
            <button @click="resetCount('reset param', $event)">Resetar</button>
        </div>
    </div>
</template>

<script>

export default {
    name: 'AppMethod',

    data() {
        return {
            contador: 0,
        }
    },

    methods: {
        incrementCount(event) {
            console.log('increment >', event);
            ++this.contador;
        },

        resetCount(param, event) {
            console.log(param, '>', event);
            this.contador = 0;
        },

        imprime() {
            console.log('RED CONTAINER')
        }
    }
}
</script>

<style lang="scss" scoped>
.red {
    background-color: red;
}
</style>
