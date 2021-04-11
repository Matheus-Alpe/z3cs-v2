<template>
    <div class="content-container">
        <sub class="component-title">Lifecycle Hooks:</sub>
        <h1>{{ titulo }}</h1>
        <input type="text" placeholder="Digite novo título..." ref="input" :value="titulo">
        <button @click="alterarTitulo">Alterar titulo</button>
        <img src="../../assets/lifecycle.png" alt="lifecycle image">
        <br>
        <button @click="destruirInstancia">Destruir instância</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            titulo: "VueJS"
        };
    },

    methods: {
        alterarTitulo() {
            const input = this.$refs.input;
            if (!input || !input.value) {
                return;
            }
            this.titulo = this.$refs.input.value;
        },

        destruirInstancia() {
            this.$destroy();
        }
    },

    activated() {
      console.log(`00.1 - activated()`)
    },

    deactivated() {
      console.log(`00.2 - deactivated()`)
    },

    beforeCreate() {
        console.log("01 - beforeCreate()");
    },

    created() {
        console.log("02 - created()");
    },

    beforeMount() {
        console.log("03 - beforeMount()");
    },

    mounted() {
        console.log("04 - mounted()");
    },

    beforeUpdate() {
        console.log("05 - beforeUpdate()");
    },

    updated() {
        console.log("06 - updated()");
    },

    beforeDestroy() {
        console.log("07 - beforeDestroy()");
    },

    destroyed() {
        console.log("08 - destroyed()");
    }
};
</script>

<style lang="scss" scoped>
img {
    margin-top: 20px;
    width: 90%;
}
</style>
