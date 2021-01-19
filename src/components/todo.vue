<template>
  <div class="container">
    <div class="top">
     <div>
       {{errorMessage}}
     </div>
      <label class="input-label">
        <input type="text" v-model="message" placeholder="текстовое поле" required>
      </label>
      <select name="priority" v-model="priority">
        <option v-for="item in items" :value="item.value" :key="item.text" > {{item.text}}</option>
      </select>
    </div>
    <button v-on:click="addTask">Добавить задачу</button>
    <ul id="task-list" class="task-list" >
      <li class="task-item" v-for="taskItem in taskItems" :key="taskItem.name" :priority="taskItem.priorityItem">
        <label>
          <input type="checkbox">
        </label>
        <p>{{taskItem.name}}</p>
      </li>
    </ul>
    <div class="bottom">
      <p>фильтры</p>
      <select name="filter-task">
        <option value="done">Сделано</option>
        <option value="notDone">Не сделано</option>
      </select>
      <select name="filter-priority">
        <option v-for="item in items" :value="item.value" :key="item.text"> {{item.text}}</option>
      </select>
    </div>
  </div>
</template>

<script>


export default {
  name: 'todo',
  data() {
    return {
      items: [
        {value: 'urgently', text: 'срочно'},
        {value: 'notUrgent', text: 'не срочно'},
        {value: 'defer', text: 'отложить'}
      ],
      message: '',
      priority: '',
      errorMessage: '',
      taskItems:[]
    }
  },
  methods:{
    addTask: function (){
      if(this.message && this.priority){
        this.taskItems.push({
          name: this.message,
          priorityItem: this.priority
        })
        this.errorMessage = ''
      } else {
        this.errorMessage = 'Заполните поля'
      }
    }
  }
}

</script>

<style>
  .container{
    margin-left: auto;
    margin-right: auto;
    max-width: 400px;
  }
  .input-label{
    display: inline-block;
    margin-right: 20px;
  }

  select{
    margin-left: 50px;
  }

  button{
    display: block;
    margin-top: 15px;
    margin-left: auto;
    margin-right: auto;
  }

  .task-list{
    list-style: none;
    display: flex;
    flex-direction: column;
    padding: 20px 0;
    margin: 0;
  }
  .task-item{
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  p{
    margin: 0;
    padding: 0;
  }
  .bottom p {
    margin-bottom: 20px;
  }
</style>
