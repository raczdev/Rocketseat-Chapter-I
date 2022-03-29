# Rocketseat-Chapter-I
Desafio 01

Resolvendo o desafio "Conceitos do React" do curso Ignite da Rocketseat.

É o primeiro desafio do Chapter I. 

O desafio consiste em Adicionar, Alterar e Excluir itens de uma lista. 
Por meio das respectivas funções, já previamente montadas, handleCreateNewTask(), handleToggleTaskCompletion() e handleRemoveTask().

Para resolver esse desafio eu utilizei de metodos básicos do react e typescript.

--Criação da função handleCreateNewTask()-- <br>
Para criar a primeira função eu, primeiramente, verifiquei se o campo de input tem algum texto, por meio da variável newTaskTitle, em seguida criei uma const com um numero random utilizando o Math.random() na const randomID (no desafio é necessario que o id seja aleatório). Logo após, chamei a função setTasks (que vem do useState([]) para setar um novo valor a variável tasks. Nesse momento eu preciso, primeiramente, setar a função com os valores antigos da variavel, assim sendo, dentro do vetor, no primeiro índice eu utilizei o ...tasks para retornar os valores anteriores. E para adicionar o novo valor no segundo índice eu passei os valores que são pedidos pela interface Task (id, title, isComplete), nesse caso o id: randomID, title: newTaskTitle (essa variavel é preenchida quando o usuário insere o texto no input), isComplete: false (no desafio é obrigatório o isComplete iniciar como false). Retornei um simples console.log caso não tenha nenhum título inserido no input e também, por fim, setei a variável newTaskTitle com setNewTaskTitle para ('') novamente, assim toda vez que alguem criar uma nova tarefa o campo será "resetado".

--Criação da função handleToggleTaskCompletion()-- <br>
Nessa função eu tive que percorrer todas as tasks utilizando um map para achar a task que o usuário quer alterar. Se a task.id tiver o mesmo id que o usuario passou, eu irei repetir a task com ...task e vou alterar o campo isComplete setando o novo valor para ser o oposto do task.isComplete. Tudo isso sendo feito dentro do método setTasks para atualizar o valor da tasks.

--Criação da função handleRemoveTask()-- <br>
Por fim, na criação dessa função eu utilizei o .filter nas tasks para guardar na variável filterTasks todas as tasks que possuem o id diferente daquele que o usuário quer excluir. E então eu setei o valor de tasks com setTasks(filterTasks) assim atualizando a lista para exibir todos os itens, menos aquele foi marcado para exclusão.
