<template>
    <v-app id="inspire" >
        <Header v-on:tuggleSidebar="drawer = !drawer"/>
        <NavBar :drawer="drawer" />

        <v-content>

        </v-content>

        <Footer/>
    </v-app>
</template>

<script>
    import Header from './components/layout/Header/Header';
    import NavBar from './components/layout/NavBar';
    import Footer from './components/layout/Footer';

    export default {
        data() {
            return {
                drawer: true,
            }
        },

        methods: {
            test(){
                console.log(1111);

            }
        //     ondrawer (data) {
        //         console.log('fffffff', data)
        //     }
        },
        components: {
            Header,
            NavBar,
            Footer
        }
    }
</script>
