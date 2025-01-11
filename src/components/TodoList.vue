<script setup lang="ts">

import ListItem from './ListItem.vue';
type Item = {
    title: string;
    checked?: boolean;
}

const GroupsItems: Item [] = [
    { title:'Leer un Libro al mes', checked: false},
    { title:'Hacer Ejercicio', checked: false},
    { title:'Aprender algo nuevo'},

];

</script>

<template>

    <ul>

        <li :key="index"   v-for="(item, index) in GroupsItems" >

            <ListItem :isChecked="item.checked" > {{ item.title }}</ListItem> 

        </li>


       <!-- <ListItem :isChecked="false" > Leer un libro al mes</ListItem> -->


    </ul>




</template>

<style scoped>






</style>
