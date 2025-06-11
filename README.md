# Linha de produção individual
O problema resolvido consistia na ordenação da produção de pedidos em uma linha de produção. Cada pedido possui um tempo de produção e um tempo para que seja entregado, de forma que caso o tempo de produção
fosse maior que o tempo especificado para sua entrega uma multa deveria ser paga baseada no atraso. A resolução do problema se dá pela elaboração de uma ordem para produção dos pedidos que minimize a multa
total a ser paga.

# Solução
A solução do problema foi representada como um _array_ com tamanho igual a quantidade de pedidos. 

# Estratégias
Para a resolução do problema, foi implementado o VDN (Variable Neighborhood Descent) e o ILS (Iterated Local Search).

## VND
Para o VDN, foram implementadas as seguintes vizinhanças:
* Reinsertion: Reinserção de blocos contendo de 1 a 13 pedidos em outro local;
* Opt: Inversão da posição de um bloco de pedidos;
* Two Swap: Troca de lugar entre dois sucos.
Sendo que a execução dos mesmos se deu nesta ordem em código.

## ILS
Para o ILS, foram implementadas as seguintes perturbações:
* Two Divide: Troca as duas metades da solução (a segunda metade se torna e primeira respeitando a ordem já existente e vice-versa);
* Rotate: Inverte toda a solução
* Multiple Swaps: Realiza a troca de 2 pedidos $x$ vezes, sendo $x$ um valor aleatório;
* Rotate Evens: Realiza o "avanço" de todos os pedidos pares da solução (o pedido 2 vira o 4, o 4 vira o 6 e assim sucessivamente).

# Execução
Para executar o código, basta rodar o comando `make` dentro do diretório e então
```
./bin/projeto_apa.exe [<num_ILS>]
```
para rodar todas as instâncias com `num_ILS` sendo o número de vezes que o ILS será executado,
```
./bin/projeto_apa.exe [<instância>] [<num_ILS>]
```
para rodar apenas a `instância` especificada, e
```
./bin/projeto_apa.exe [<instância>] [<num>] [<num_ILS>]
```
para rodar aquela `instância` `num` vezes.
