<script>
  import { todos } from '~/store'
  import CreateTodo from '~/components/CreateTodo'
  import Todo from '~/components/Todo'

  const storageTodos = localStorage.getItem('todos')
  if (storageTodos) {
    $todos = JSON.parse(storageTodos)
  }
</script>

<div class="container">
  <div class="title">
    기록해서 까먹지 말기
  </div>
  <div class="sub-title">
    궁큰!
  </div>
  <CreateTodo />
  <div class="todos">
    {#each $todos as todo (todo.id)}
      <Todo {todo} />
    {/each}
  </div>
</div>

<style lang="scss">
  .title {
    font-family: "Roboto", sans-serif;
    font-weight: 700;
    font-size: 30px;
    color: rgb(34, 34, 34);    
    margin: 20px 0 0;
    border-radius: 5px;
    background-color: #9d9d9d;  

    display: flex;
    align-items: center;
    justify-content: center;
  }
  .sub-title{
    font-family: "Roboto", sans-serif;
    font-weight: 700;
    font-size: 30px;
    color: rgb(109, 4, 4);    
    margin: 20px 0 0;  

    display: flex;    
    justify-content: center;
  }
  .todos {
    padding: 20px 0;
  }
</style>
