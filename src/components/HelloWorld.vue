<template>
  <div class="container">
    <div class="top">
      <label class="input-label">
        <input type="text" placeholder="текстовое поле">
      </label>
      <select name="type" id="">
        <option value="urgently">срочно</option>
        <option value="notUrgent">не срочно</option>
        <option value="defer">отложить</option>
      </select>
    </div>
    <button>Добавить задачу</button>
    <ul class="task-list">
      <li class="task-item">
        <label>
          <input type="checkbox">
        </label>
        <p>text</p>
      </li>
      <li class="task-item">
        <label>
          <input type="checkbox">
        </label>
        <p>text</p>
      </li>
    </ul>
    <div class="bottom">
      <p>фильтры</p>
      <select name="filter-task">
        <option value="done">Сделано</option>
        <option value="notDone">Не сделано</option>
      </select>
      <select name="filter-type">
        <option value="urgently">срочно</option>
        <option value="notUrgent">не срочно</option>
        <option value="defer">отложить</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld'
}
</script>

<style scoped>
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
