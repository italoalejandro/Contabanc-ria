# Simulador de conta bancária com limite de saques diários

saldo_inicial = 1000
saldo = saldo_inicial
limite_saques_diarios = 3
saques_realizados = 0

while True:
    print("\nEscolha uma opção:")
    print("1. Saque")
    print("2. Depósito")
    print("3. Ver saldo")
    print("4. Sair")
    
    opcao = input("Digite o número da opção: ")

    if opcao == '1':
        if saques_realizados < limite_saques_diarios:
            saque = float(input('Digite o valor do saque: '))
            print("-----------------")

            if saque <= saldo:
                print('Saque realizado com sucesso!')
                saldo -= saque
                saques_realizados += 1
            else:
                print('Saldo insuficiente!')
        else:
            print('Limite de saques diários atingido!')

    elif opcao == '2':
        deposito = float(input('Digite o valor do depósito: '))
        print("-----------------")

        if deposito > 0:
            saldo += deposito
            print('Depósito realizado com sucesso!')
        else:
            print('Valor de depósito inválido!')

    elif opcao == '3':
        print(f'Saldo atual: {saldo}')

    elif opcao == '4':
        print("Saindo do sistema...")
        break

    else:
        print("Opção inválida!")

    print("-----------------")
