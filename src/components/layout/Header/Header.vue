<template>
    <v-app-bar app color="indigo" dark>
        <v-app-bar-nav-icon @click="tuggleshow"/>
        <v-toolbar-title>Application</v-toolbar-title>
        <v-spacer/>
        <v-speed-dial id="create" v-model="fab" top="bottom" right direction="top" transition="scale-transition">
            <template v-slot:activator>
                <v-btn v-model="fab" color="blue darken-3" dark fab>
                    <v-icon v-if="fab">mdi-close</v-icon>
                    <v-icon v-else>mdi-account-circle</v-icon>
                </v-btn>
            </template>
            <v-btn fab dark small color="green">
                <v-icon>mdi-pencil</v-icon>
            </v-btn>
            <v-btn fab dark small color="indigo">
                <v-icon>mdi-plus</v-icon>
            </v-btn>
            <v-btn
                    fab
                    dark
                    small
                    color="red"
            >
                <v-icon>mdi-delete</v-icon>
            </v-btn>
        </v-speed-dial>

    </v-app-bar>

</template>

<script>

    export default {
        name: 'Header',

   /*     props: {
            drawer:  Boolean,
        },*/
        data: () => ({
            direction: 'top',
            fab: false,
            fling: false,
            hover: false,
            tabs: null,
            top: false,
            right: true,
            bottom: true,
            left: false,
            transition: 'slide-y-reverse-transition',
        }),
        methods: {

            tuggleshow(){
               // console.log(22);
                this.$emit('tuggleSidebar');
            },
        },
        computed: {
            activeFab () {
                switch (this.tabs) {
                    case 'one': return { class: 'purple', icon: 'account_circle' }
                    case 'two': return { class: 'red', icon: 'edit' }
                    case 'three': return { class: 'green', icon: 'keyboard_arrow_up' }
                    default: return {}
                }
            },
        },
    };
</script>
<style>
    #create .v-speed-dial {
        position: relative;
    }

    #create .v-btn--floating {
        position: relative;
    }
</style>