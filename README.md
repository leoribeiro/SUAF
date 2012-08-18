Simulador Universal de Autômatos Finitos

Foi desenvolvido um simulador universal de Autômatos Finitos que receba os dados do autômato que deseja simular junto com uma série de cadeias de símbolos em um arquivo de entrada.

Deve-se preencher um arquivo de saída com o resultado. Para exercutar o algoritmo deve-se ter um interpretador python e executar:

$ python reconhece_automato_finito.py entrada.txt saída.txt

Onde o primeiro parâmetro é um arquivo com os dados da entrada e o segundo é o nome do arquivo que será criado com a resposta.

Foi escolhida a linguagem python pela sua simplicidade e rapidez em desenvolver um programa.

As técnicas utilizadas foram:

O Algoritmo lê o arquivo de entrada com as informações para montar o autômato e armazena estas informações em variáveis e em estruturadas de dados como a lista (list).

Cada transição do autômato é uma lista onde a primeira posição é o estado de origem, a segunda posição é o símbolo e a terceira posição é o estado de destino. E todas as transições são armazenas em uma lista.

Ex: transição Q1 x Q2 é armazenada em uma lista [1, ‘x’, 2]


Função validaCadeiaSimbolos(cadeia,estado)

A solução desenvolvida tem uma função validaCadeiaSimbolos onde é passada uma cadeia lida do arquivo e o estado inicial que se deseja que se inicie o reconhecimento da cadeia. Se parece um pouco com um analisador sintático recursivo.

A função é uma função recursiva que verifica as transições e para cada caracter da cadeia, verifica se o mesmo consegue ser reconhecido pelo estado atual onde a função está. Se chegar a condição de parada da função que é o fim da cadeia lida e o estado corrente do autômato é um estado final, a função retorna True significando que o cadeia de símbolos foi reconhecida. Se o estado atual não for final, a função retorna False.


Função testaCadeia(cadeia)

Esta função recebe uma cadeia de símbolos para verificar se esta cadeia pode ser reconhecida pelo autômato.

Na função existe um laço de repetição que invoca a função validaCadeiaSimbolos passando como parâmetro a cadeia a ser verificada e todos os estados iniciais do autômato.

Desta forma, consegue-se testar se o autômato valida a cadeia por todos os estados iniciais. Se alguma chamada da função validaCadeiaSimbolos retornar True, a função testeCadeia retornará True, significando que a cadeia foi reconhecida.

Se após todos os estados iniciais testados não houver nenhum retorno True, a função testeCadeia retorna False.

Como o problema foi resolvido recursivamente, o algoritmo tende a consumir mais tempo e memória do que uma solução interativa por exemplo.

