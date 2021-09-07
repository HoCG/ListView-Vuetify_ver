<template>
    <v-card id="app" class="mx-auto" max-width="500">
        <v-toolbar color="teal" dark="dark">
            <v-app-bar-nav-icon></v-app-bar-nav-icon>

            <v-toolbar-title>Topics</v-toolbar-title>

            <v-spacer></v-spacer>
            <!--<v-list>
                <v-list-group
                    v-for="item in dept"
                    :key="item.title"
                    v-model="item.active"
                    :prepend-icon="item.action"
                    no-action="no-action">
                    <template v-slot:activator="v-slot:activator">
                        <v-list-item-content>
                            <v-list-item-title v-text="item.title"></v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="child in item.dept" :key="child.title">
                        <v-list-item-content>
                            <v-list-item-title v-text="child.title"></v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list-group>
            </v-list>-->
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
</style>