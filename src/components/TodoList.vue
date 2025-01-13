<script setup lang="ts">
    import { ref } from 'vue' ; 
    import type { Ref } from 'vue' ; 

    import ListItem from './ListItem.vue';

    type Item = {
        title: string;
        checked?: boolean;
    }



   
    const GroupsItems: Ref<Item[]> = ref([
        { title:'Leer un Libro al mes', checked: false },
        { title:'Hacer Ejercicio', checked: false },
        { title:'Aprender algo nuevo', checked: false },

    ]);


    const updateItem = (element: Item): void => {
        const updatedItem = findItemList(element)
        if(updatedItem) {
            toggleItemChecked(updatedItem);
        }
    }



    const findItemList = (element: Item): Item | undefined => {
        return GroupsItems.value.find((elementItemInList) => elementItemInList.title === element.title );

    }



   /* const toggleItemChecked = (element: Item): void => {
        element.checked != element.checked;

    }*/

    const toggleItemChecked = (element: Item): void => {
        element.checked = !element.checked;
    }



</script>

<template>

    <ul>

        <li :key="index"   v-for="(element, index) in GroupsItems" >

            <ListItem :isChecked="element.checked"  @updateItem="() => updateItem(element)" > 
                {{ element.title }}


            </ListItem> 

        </li>


       <!-- <ListItem :isChecked="false" > Leer un libro al mes</ListItem> -->


    </ul>

 


</template>

<style scoped>

    ul {
        list-style: none;
        padding: 2;
    }

    li {
        margin: 0.5rem 0;
    }



</style>
