<template>
    <header>
        <h1>{{ title }}</h1>
        <Button 
            v-show="homePage"
            @btn-click="$emit('toggle-add-task')" 
            :text= "showAddTask ? 'Close' : 'Add' "
            :color="showAddTask ? 'red': 'green'"
        />
        <!-- <Button text="Update Task" color="blue"/>
        <Button text="Delete Task" color="red"/> -->
    </header>
</template>

<script>
import Button from './Button.vue'
    export default {
        name: 'Header',
        props: {
            title: String,
            showAddTask: Boolean
        },
        components: {
            Button
        },
        // Used for reactivity e.g combining first name and last name data to get the full name
        computed: {
            homePage() {
                if(this.$route.path === '/') {
                    return true
                } else {
                    return false
                }
            }
        }
    }
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>