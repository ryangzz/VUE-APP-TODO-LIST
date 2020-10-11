<template>
    <div class="comp">
        <h3>Completed</h3>
        <div class="task" v-for="(task, index) of tasks" :key="index">{{task.task}}<i class="fas fa-trash-alt" @click="deleteTask(index)"></i></div>
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
    methods: {
        deleteTask(index){
            this.$emit('delete', index);
        }
    },
}
</script>

<style scoped>
    
</style>