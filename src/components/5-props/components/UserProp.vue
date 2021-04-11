<template>
    <div class="content-container">
        <sub class="component-title">Component: User</sub>
        <h1>Nome: {{ customPropUser.nome }}</h1>
        <h2>Time: {{ customPropUser.time }}</h2>
        <h5>Data Nascimento: {{ customPropUser.dataNascimento }}</h5>
    </div>
</template>

<script>
export default {
    name: 'UserProp',

    //------- props: ['customPropUser']
    props: {


        //------- customPropUser: Object



        //------- customPropUser: [Object, String]








        customPropUser: {
            type: Object,
            default() {
                return {
                    nome: 'Default',
                    time: 'Linx',
                    dataNascimento: '01/01/2000'
                }
            },
            // required: true,

            // validator(user) {
            //     return user['nome'].includes('Matheus')
            // }
        }
    }
}

/*

    Tipos:

    -   String
    -   Number
    -   Boolean
    -   Array
    -   Object
    -   Date
    -   Function
    -   Symbol

*/
</script>
