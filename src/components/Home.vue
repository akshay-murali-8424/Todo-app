<template>
  <div>
    <h1>TODO APP USING VUE</h1>
    <div>
      <input
        type="text"
        placeholder="type something"
        class="my-input"
        v-model="toDo"
      />
      <button class="my-button" @click="addToDo(toDo)">add</button>
    </div>
    <div>
        <ToDoCard  v-for="(element,i) in toDos" :to-dos="toDos"  :key="i"  :todo="element" :index="i"/>  
    </div>
  </div>
</template>

<script>
import ToDoCard from './ToDoCard.vue';

export default{
    name: "Home",
    data(){
        return{
            toDo:'',
            toDos:[]
        }
    },
    methods:{
        addToDo(toDo){
            if(toDo.trim()){
                this.toDos.push(toDo) 
                this.toDo=''
            }
        },
    },
    components: { ToDoCard }
}
</script>

<style >
 .my-input {
  padding: 12px;
  border-radius: 5px;
  border: none;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}

.my-button {
  padding: 10px;
  border-radius: 5px;
  background-color: #2c3e50;
  color: #fff;
  font-weight: 400;
  border: none;
} 


</style>
