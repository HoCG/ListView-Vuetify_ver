<template>
    <v-card id="app" class="mx-auto" max-width="500">
        <v-toolbar color="teal" dark="dark">
            <v-app-bar-nav-icon></v-app-bar-nav-icon>
            <v-toolbar-title>Topics</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon="icon">
                <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
        </v-toolbar>
        <tree :data="dept"></tree>
    </v-card>
</template>

<script>
    import OrganizationsData from "./assets/Organizations.json"
    import Tree from "./components/Tree";
    export default {
        name: 'App',
        components: {
            Tree
        },
        data: () => ({dept: OrganizationsData.result})
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
    i{
        color: black !important;
    }
</style>