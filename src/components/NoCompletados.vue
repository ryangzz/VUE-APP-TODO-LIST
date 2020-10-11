<template>
    <div class="notcomp">
        <h3>Not Completed</h3>
        <div class="task" v-for="(tks, index) of tasks" :key="index">{{tks.task}}
            <i class="fas fa-trash-alt" @click="deleteTask(index)"></i><i class="fas fa-check" @click="complete(index)"></i>
        </div>
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
        complete(index){
            this.$emit('action', index);
        },
        deleteTask(index){
            this.$emit('delete', index);
        }
    },
}
</script>
<style scoped>
    
</style>