<template v-slot:default="{ active }">
    <v-list>
        <v-list v-for="item in treeData" :key="item.title" no-action="no-action">
            <v-list v-if="item.dept !== null">
                <v-list-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-icon>
                                &nbsp;&nbsp;&nbsp;&nbsp;
                                <v-icon>mdi-home</v-icon>
                                <v-list-item-title v-text="item.title"></v-list-item-title>
                            </v-list-item-icon>
                        </v-list-item-content>
                    </template>
                    <mynode :treeData="item.dept"/>
                </v-list-group>
            </v-list>
            <!--최하위값들-->
            <v-list v-else>
                <v-list-item-content>
                    <v-list-item-icon>
                        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                        <v-icon class="EndIcon">mdi-star</v-icon>
                        <v-list-item-title v-text="item.title"></v-list-item-title>
                        <!--v-expansion-panel을 여기에 적용시키는것을 고려해보자.-->
                    </v-list-item-icon>
                </v-list-item-content>
            </v-list>
        </v-list>
    </v-list>
</template>

<script>
    export default {name: "mynode", props: ["treeData"]};
</script>
<style>
    .v-list-item__title {
        float: left;
    }
    .EndIcon{
        color: yellow !important;
    }
</style>