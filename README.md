# Sistema de Gerenciamento de Conta Bancária

Este projeto é um exemplo de um sistema básico de gerenciamento de conta bancária em Python. Ele permite ao usuário realizar operações bancárias essenciais, como depósitos, saques e consulta ao extrato da conta.

## Funcionalidade

O sistema oferece um menu interativo com as seguintes opções:

- **[d]** - Depósito
- **[s]** - Saque
- **[e]** - Extrato
- **[q]** - Sair

## Como Funciona

### Variáveis Iniciais

- `saldo` (float): Inicialmente `0`. Representa o saldo atual da conta.
- `limite` (float): Inicialmente `500`. Limite máximo para saques.
- `extrato` (str): Inicialmente vazio. Armazena o histórico de operações.
- `numero_saques` (int): Inicialmente `0`. Conta o número de saques realizados.
- `LIMITE_SAQUES` (int): Inicialmente `3`. Número máximo de saques permitidos.

### Operações Disponíveis

1. **Depósito** (`d`):
   - Solicita o valor do depósito.
   - Adiciona o valor ao saldo e registra no extrato se for positivo.
   - Exibe mensagem de erro se o valor for inválido.

2. **Saque** (`s`):
   - Solicita o valor do saque.
   - Verifica se o valor excede o saldo, o limite ou o número máximo de saques.
   - Exibe mensagens de erro apropriadas se alguma condição não for atendida.
   - Registra o saque no extrato se for permitido.

3. **Extrato** (`e`):
   - Exibe o histórico de operações realizadas.
   - Se não houver movimentações, exibe mensagem informando a ausência de operações.

4. **Sair** (`q`):
   - Encerra o programa.

5. **Operação Inválida**:
   - Exibe mensagem de erro para opções inválidas.

## Código

Aqui está o código principal:

```python
menu = """

[d]
[s]
[e]
[q]

=> """

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:
    opcao = input(menu)

    if opcao == "d":
        valor = float(input("Informe o valor do depósito: "))
        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"
        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "s":
        valor = float(input("Informe o valor do saque: "))
        excedeu_saldo = valor > saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES
        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente.")
        elif excedeu_limite:
            print("Operação falhou! O valor do saque excede o limite.")
        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedido.")
        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1
        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "e":
        print("\n================EXTRATO================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nsaldo: R$ {saldo:.2f}")
        print("==========================================================")

    elif opcao == "q":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")





