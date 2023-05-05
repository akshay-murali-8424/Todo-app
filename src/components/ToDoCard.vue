<template>

<div class="card">
  <div>
    {{ todo }}
  </div>
  <div>
    <button @click="removeToDo(index)" class="my-button">done</button>
  </div>
</div>

</template>

<script>
  export default {
    name:"toDoCard",
    props:{
        todo: {type:String,required:true},
        index:{type:Number,required:true},
        toDos:{type:Array,required:true}
    },
    methods:{
      removeToDo(index){
              this.toDos.splice(index,1)
      }
    }
  }
</script>


<style>

.card{
  display: flex;
  justify-content: space-between;
  padding: 12px;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  width: 20%;
  border-radius: 12px;
  margin: 1rem;
  margin-left: auto;
  margin-right: auto;
}



</style>

