README: Sistema de Gerenciamento de Conta Bancária
Este código é um exemplo de um simples sistema de gerenciamento de conta bancária em Python. O sistema permite ao usuário realizar operações bancárias básicas, incluindo depósitos, saques e a visualização do extrato da conta.

Funcionalidade
O sistema oferece um menu interativo com as seguintes opções:

[d] - Depósito
[s] - Saque
[e] - Extrato
[q] - Sair
Descrição do Código
Variáveis Iniciais
saldo (float): Inicialmente definido como 0. Representa o saldo atual da conta.
limite (float): Inicialmente definido como 500. Representa o limite máximo para saques.
extrato (str): Inicialmente uma string vazia. Armazena o histórico das operações realizadas.
numero_saques (int): Inicialmente definido como 0. Conta o número de saques realizados.
LIMITE_SAQUES (int): Inicialmente definido como 3. Representa o número máximo de saques permitidos.
Fluxo do Programa
Menu de Opções: O menu é exibido continuamente até que o usuário escolha sair.
Depósito:
O usuário é solicitado a informar o valor do depósito.
O valor é adicionado ao saldo e registrado no extrato se for positivo.
Caso o valor seja inválido (menor ou igual a zero), uma mensagem de erro é exibida.
Saque:
O usuário é solicitado a informar o valor do saque.
O sistema verifica se o valor do saque excede o saldo, o limite ou o número máximo de saques permitidos.
Se qualquer uma dessas condições for verdadeira, uma mensagem de erro é exibida.
Caso contrário, o valor é subtraído do saldo e registrado no extrato.
Se o valor informado for inválido, uma mensagem de erro é exibida.
Extrato:
O extrato das operações realizadas é exibido.
Se nenhuma movimentação foi realizada, uma mensagem informando que não houve movimentações é exibida.
Sair:
O loop é interrompido e o programa é encerrado.
Operação Inválida:
Se o usuário inserir uma opção que não está no menu, uma mensagem de erro é exibida.
Como Executar
Copie o código fornecido para um arquivo Python, por exemplo, banco.py.
Execute o arquivo Python utilizando um interpretador Python (Python 3.x é recomendado):
sh
Copiar código
python banco.py
Siga as instruções exibidas no menu para realizar operações bancárias.
Exemplo de Uso
plaintext
Copiar código
[d]
[s]
[e]
[q]

=> d
Informe o valor do depósito: 150
=> s
Informe o valor do saque: 200
Operação falhou! O valor do saque excede o limite.
=> e

================EXTRATO================
Depósito: R$ 150.00

saldo: R$ 150.00
==========================================================
=> q
Observações
Certifique-se de fornecer valores numéricos válidos para depósitos e saques.
O sistema não lida com exceções de entrada, então fornecer valores não numéricos pode causar erros.
Contribuições
Contribuições para melhorar o código são bem-vindas. Para sugestões ou melhorias, por favor, entre em contato.

Este README cobre a funcionalidade, o fluxo do programa e orientações para executar o código. Se precisar de mais detalhes ou ajustes, sinta-se à vontade para perguntar!




