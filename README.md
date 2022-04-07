# Rocketseat-Chapter-I
## <a href="https://www.notion.so/Desafio-01-Conceitos-do-React-51e4099a6e2f4d4bae94f9fe75bb769d">Challenge</a>: React Concepts
<img src="https://img.shields.io/badge/react%20-%2320232a.svg?&style=plastic&logo=react&logoColor=%2361DAFB"/><img src="https://img.shields.io/badge/typescript%20-%23007ACC.svg?&style=plastic&logo=typescript&logoColor=white"/>

### The challenge is to make the user: 
- should be able to add a task
- should not be able to add a task with a empty title
- should be able to remove a task
- should be able to check a task

#### Function to add a new task
```
function handleCreateNewTask() {
    if (newTaskTitle !== "") { //Checks if the input actually has a task title.
      const randomID = Math.random(); //Make a random number for the id.

      setTasks([
        ...tasks, //Spread syntax to combine two arrays, all tasks and the new array.
        {
          id: randomID,
          title: newTaskTitle, //The new array. 
          isComplete: false,
        },
      ]);
    } else {
      return console.log("Não tem título"); 
    }

    setNewTaskTitle(""); //Set the value of newTaskTitle to the default, " ".
  }
```
#### Function to check a task
```
function handleToggleTaskCompletion(id: number) { //The function receives the id of the task.
    setTasks(
      tasks.map((task) => //Map all the tasks.
        task.id === id  //Check if the tasks id matches the id that has been given to the function.
          ? {
              ...task,  //If it matches, then we repeat the task with spread syntax.
              isComplete: !task.isComplete, //And we set a new value to the isComplete const. 
            }
          : task //If it does not match, we just simply reapet the same value of the task
      )
    );
}
```
#### Function to delete a task
```
function handleRemoveTask(id: number) { //The function receives the id of the task.
    const filterTasks = tasks.filter((task) => task.id !== id); //Filter all the tasks and save the ones who have a 
                                                                different id to the one given in the function.
                                                                  
    setTasks([...filterTasks]); //Set the value of the tasks to be the filtered tasks before.
}
```
