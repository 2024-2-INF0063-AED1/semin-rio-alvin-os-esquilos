# Gerenciador de Tarefas - Trabalho de Estruturas de Dados

## Introdução

### Descrição

Este projeto é um gerenciador de tarefas desenvolvido em *C* como parte do trabalho da disciplina *INF0063 - AED1 (Algoritmos e Estruturas de Dados I). O sistema permite que o usuário adicione tarefas, acompanhe o progresso e registre as tarefas concluídas, além de calcular o **XP* ganho ao completar as tarefas. A implementação utiliza estruturas de dados como *fila* e *lista encadeada* para gerenciar as tarefas pendentes e concluídas.

![img](https://amhandmade.pt/cdn/shop/files/IMG_5474.jpg?v=1695566664&width=1445)

---

## Fundamentos Teóricos

### Estruturas de Dados Utilizadas

   - Fila de Tarefas Pendentes (Queue):
      * A fila é utilizada para armazenar as tarefas que ainda não foram concluídas, seguindo o conceito de FIFO (First In, First Out). Novas tarefas são adicionadas ao final da fila, e a conclusão remove tarefas do início.
      * Implementação: Cada tarefa é representada como um nó da estrutura, com ponteiros que conectam os nós consecutivamente.

   - Lista de Tarefas Concluídas:
      * A lista ligada é usada para armazenar tarefas já concluídas, com inserção de novas tarefas no início da lista (ordem LIFO - Last In, First Out). Cada nó aponta para o próximo elemento na lista.

### Mecanismos e Algoritmos

   - Adição de Tarefas à Fila:
      * O método adicionarTarefaFila verifica se a tarefa já existe (para evitar duplicatas) usando o algoritmo de busca linear, comparando a descrição da nova tarefa com as existentes.
      * Caso a tarefa seja única, ela é alocada dinamicamente e inserida na fila.

   - Exibição das Tarefas:
      * As funções exibirTarefas e exibirTarefasConcluidas iteram pelas estruturas de dados e formatam os dados das tarefas em uma tabela organizada.
      * Esse recurso melhora a visualização, fundamental para monitorar progresso.

   - Conclusão de Tarefas:
      * O método concluirTarefa permite ao usuário selecionar uma tarefa por meio de um índice, com base na listagem atual.
      * Após a conclusão:
         * Atualiza-se o tempo real dedicado à tarefa.
         * O sistema calcula o XP ganho (1 XP para cada 10 minutos de trabalho).
         * A tarefa é removida da fila e inserida na lista de tarefas concluídas.

   - XP Total:
      * O cálculo do XP total acumulado considera as tarefas concluídas e é armazenado em uma variável global compartilhada.

   - Gerenciamento de Memória:
      * O código utiliza funções como malloc e free para gerenciar a memória dinamicamente. Isso permite a criação e remoção de tarefas sem desperdício de memória.

### Avaliação da Solução
A avaliação do sistema pode ser feita com base nas seguintes métricas:
   - Funcionalidade:
      * Verificar se as operações básicas (adicionar, concluir e exibir tarefas) funcionam conforme esperado.
      * Testar cenários de erro, como inserção de tarefas duplicadas ou escolha de tarefas inexistentes.
   - Desempenho:
      * Avaliar a eficiência dos algoritmos usados para manipulação de tarefas, especialmente a busca linear para verificar duplicatas e o gerenciamento da fila.
      * Considerar o tempo de execução em cenários com muitas tarefas.
   - Utilização de Recursos:
      * Garantir que a memória alocada é liberada adequadamente para evitar memory leaks.
      * Analisar o consumo de memória com ferramentas específicas.
   - Usabilidade:
      * Testar a interface com o usuário, validando se as mensagens e fluxos são claros.
      * Observar a facilidade de navegação entre as opções do menu.
   - Escalabilidade:
      * Medir o comportamento do sistema com volumes crescentes de tarefas pendentes e concluídas.

### Forma de Avaliação
Para validar e melhorar a solução, podem ser aplicadas as seguintes estratégias:
   - *Testes unitários: Validar individualmente cada função (e.g., *adicionarTarefaFila, concluirTarefa).
   - *Cenários de uso reais*: Simular casos típicos e extremos de uso, como adicionar uma grande quantidade de tarefas.
   - *Ferramentas de monitoramento*: Utilizar ferramentas como Valgrind para verificar vazamentos de memória e depurar o uso de ponteiros.
   - *Feedback de usuários*: Coletar opiniões sobre a experiência e possíveis melhorias.

---

## Metodologia

### Funcionalidades

![img](https://midias.siteware.com.br/wp-content/uploads/2019/05/25081155/dicas-gestao-projetos.jpg)


- *Adicionar Tarefas:* O usuário pode adicionar tarefas com uma descrição e tempo estimado para a sua execução.
- *Exibir Tarefas Pendentes:* Lista todas as tarefas ainda não concluídas.
- *Concluir Tarefas:* O usuário pode marcar uma tarefa como concluída e registrar o tempo real dedicado à tarefa.
- *Exibir Tarefas Concluídas:* Exibe uma lista de tarefas já concluídas, com o tempo estimado, tempo real e XP ganho.
- *Ver XP Total:* O sistema calcula e exibe o total de XP ganho até o momento.
- *Controle de Entrada:* O sistema evita a duplicação de tarefas com a mesma descrição.

### Estruturas de Dados Utilizadas

- *Fila:* Utilizada para armazenar as tarefas pendentes. A fila segue a estrutura *FIFO* (First In, First Out), onde a tarefa que é adicionada primeiro será a primeira a ser concluída.
- *Lista Encadeada:* Utilizada para armazenar as tarefas concluídas. Cada tarefa concluída é inserida no início da lista.

### Estrutura do Código

- *Tarefa:* Estrutura que armazena os dados de cada tarefa, como descrição, XP, tempo estimado, tempo real e ponteiro para a próxima tarefa.
- *Fila:* Estrutura que mantém as tarefas pendentes. Contém ponteiros para o início (frente) e fim (traseira) da fila.
- *ListaConcluidas:* Estrutura que mantém as tarefas concluídas, com um ponteiro para o início da lista.

### Como Usar

1. *Adicionar Tarefas:* O programa pede ao usuário a descrição da tarefa e o tempo estimado para sua execução.
2. *Exibir Tarefas Pendentes:* Mostra todas as tarefas pendentes, incluindo descrição, XP acumulado, tempo estimado e tempo real.
3. *Concluir Tarefas:* O usuário seleciona uma tarefa pendente para marcar como concluída, informa o tempo real dedicado e ganha XP.
4. *Exibir Tarefas Concluídas:* Exibe uma lista das tarefas concluídas com o tempo real dedicado e o XP acumulado.
5. *Ver XP Total:* Mostra o total de XP acumulado até o momento.

### Como Compilar e Executar

1. *Compilar o código:*
   bash
   gcc -o Codigo Codigo.c
   

2. *Executar o programa:*
   bash
   ./Codigo.c
   

3. Siga as instruções no menu interativo para adicionar tarefas, concluí-las, verificar tarefas pendentes ou concluídas, e ver o XP total.

### Exemplo de Saída


1. Adicionar Tarefa
2. Exibir Tarefas
3. Marcar Tarefa como Concluída
4. Ver Tarefas Concluídas
5. Ver XP Total
6. Sair
Escolha uma opção: 1
Digite a descrição da tarefa: Estudar Estruturas de Dados
Digite o tempo estimado dedicado à tarefa (em minutos): 60
Deseja adicionar outra tarefa? (s/n): s
Digite a descrição da tarefa: Revisar Algoritmos
Digite o tempo estimado dedicado à tarefa (em minutos): 45
Deseja adicionar outra tarefa? (s/n): n


## Resultados e Conclusões

Os resultados mostram que o gerenciador de tarefas opera corretamente, com adição, conclusão e exibição funcionando conforme esperado. Em testes simulando 20 tarefas, o XP total foi calculado corretamente, e a exibição foi clara e organizada. Não foram detectados memory leaks em testes com o Valgrind, garantindo eficiência no uso de memória. Comparado a soluções similares, o sistema se destacou pela simplicidade de uso e clareza. Como lição, aprendemos a importância de validar cenários extremos, usar boas práticas de gerenciamento de memória e estruturar menus intuitivos para a experiência do usuário.

## Equipe

- *202302520 - Ana Clara Fortunado de Souza*
- *202201646 - Layssa Ribeiro Abreu Peres*
- *202206139 - Thiago Honorato Ferreira*

## Licença

Este projeto é licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.