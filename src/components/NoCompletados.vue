<template>
    <div class="notcomp">
        <h3>Not Completed</h3>
        <div class="task" v-for="tks of tasks">{{tks.task}}<i class="fas fa-trash-alt"></i><i class="fas fa-check"></i></div>
    </div>
</template>
<script>
export default {
    props:{
        tareas:Object
    },
    data() {
        return {
            tasks:this.tareas
        }
    },
}
</script>
<style scoped>
    
</style>