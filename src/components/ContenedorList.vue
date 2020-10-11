<template>
    <div class="container">
        <input type="text" class="txtb" placeholder="Add a task" v-model="txtTask" @keyup.enter.prevent="addTask">
        <NoCompletados :tareas="tasksNoComplete" @action="addTaskComplete" @delete="deleteTaskNoComplete"/>
        <Completados :tareas="tasksComplete" @delete="deleteTaskComplete"/>
    </div>
</template>

<script>
import NoCompletados from './NoCompletados.vue'
import Completados from './Completados.vue'
export default {
    data() {
        return {
            txtTask:"",
            tasksNoComplete:[],
            tasksComplete:[],
        }
    },
    methods: {
        addTask(){
            let task = this.txtTask;
            if(task!=""){
                this.tasksNoComplete.push({task, status:true});
            }
            this.txtTask = "";
        },
        addTaskComplete(index){
            this.tasksComplete.push(this.tasksNoComplete[index]);
            this.tasksNoComplete.splice(index, 1);
        },
        deleteTaskNoComplete(index){
            this.tasksNoComplete.splice(index, 1);
        },
        deleteTaskComplete(index){
            this.tasksComplete.splice(index, 1);
        },
    },
    components:{
        NoCompletados,
        Completados
    }
}
</script>
<style>
.container{
max-width: 800px;
margin: auto;
padding: 10px;
}

.txtb{
    width: 100%;
    border: none;
    border-bottom: 2px solid #000;
    background: none;
    padding: 10px;
    outline: none;
    font-size: 18px;
}

h3{
    margin: 10px 0;
}

.task{
    width: 100%;
    background: rgba(255,255,255,0.5);
    padding: 18px;
    margin: 6px 0;
    overflow: hidden;
}

.task i{
    float: right;
    margin-left: 20px;
    cursor: pointer;
}

.comp .task{
    background: rgba(0,0,0,.5);
    color: #fff;
}
</style>