<template>
    <v-list>
        <v-list-group v-for="item in data" :key="item.title" no-action="no-action">
            <template v-slot:activator>
                <v-list-item-content>
                    <v-list-item-title v-text="item.title"></v-list-item-title>
                </v-list-item-content>
            </template>
            <node-tree :treeData="item.dept"/>
        </v-list-group>
    </v-list>
    <!--<ul> <li :key="idx" v-for="(item,idx) in treeData"> {{ item.name }} <my-node
    :treeData="item.children"/> </li> </ul> -->
</template>

<script>
import NodeTree from "./NodeTree";

export default {
  props: ["data"],
  components: {
    NodeTree
  }
};
</script>