# sistema-banc-rio
class ContaBancaria:
    def __init__(self, numero_conta, nome_cliente):
        self.numero_conta = numero_conta
        self.nome_cliente = nome_cliente
        self.saldo = 0.0

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            print(f'Depósito de R${valor:.2f} realizado com sucesso.')
        else:
            print('Valor de depósito deve ser maior que zero.')

    def sacar(self, valor):
        if 0 < valor <= self.saldo:
            self.saldo -= valor
            print(f'Saque de R${valor:.2f} realizado com sucesso.')
        else:
            print('Saque inválido. Verifique o saldo e o valor solicitado.')

    def verificar_saldo(self):
        print(f'Saldo atual: R${self.saldo:.2f}')

def menu():
    print("\nMenu:")
    print("1. Depositar")
    print("2. Sacar")
    print("3. Verificar Saldo")
    print("4. Sair")

def main():
    print("Bem-vindo ao Sistema Bancário!")
    numero_conta = input("Digite o número da conta: ")
    nome_cliente = input("Digite o nome do cliente: ")
    conta = ContaBancaria(numero_conta, nome_cliente)

    while True:
        menu()
        opcao = input("Escolha uma opção: ")

        if opcao == '1':
            valor = float(input("Digite o valor a ser depositado: "))
            conta.depositar(valor)
        elif opcao == '2':
            valor = float(input("Digite o valor a ser sacado: "))
            conta.sacar(valor)
        elif opcao == '3':
            conta.verificar_saldo()
        elif opcao == '4':
            print("Saindo do sistema. Até logo!")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()
