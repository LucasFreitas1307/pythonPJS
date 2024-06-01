import json

# Função para criar um novo arquivo de credenciais
def criar_arquivo_credenciais():
    credenciais = {'login': '', 'senha': ''}
    with open('credenciais.json', 'w') as file:
        json.dump(credenciais, file)

# Função para registrar/login
def registrar_ou_logar():
    # Verificar se o arquivo de credenciais existe
    try:
        with open('credenciais.json', 'r') as file:
            credenciais = json.load(file)
    except FileNotFoundError:
        print("Arquivo de credenciais não encontrado. Criando um novo...")
        criar_arquivo_credenciais()
        return registrar_ou_logar()

    login = input("Digite seu login: ")
    senha = input("Digite sua senha: ")

    # Se as credenciais forem válidas, permitir o acesso
    if login == credenciais['login'] and senha == credenciais['senha']:
        print("Login bem sucedido!")
        exibir_saldo_credito(login)
    else:
        print("Credenciais inválidas. Tente novamente.")
        registrar_ou_logar()

# Função para exibir saldo e crédito disponível
def exibir_saldo_credito(login):
    # Carregar os saldos do arquivo
    try:
        with open('saldos.json', 'r') as file:
            saldos = json.load(file)
    except FileNotFoundError:
        print("Arquivo de saldos não encontrado.")
        return

    # Verificar se o usuário tem um saldo registrado
    if login in saldos:
        saldo = saldos[login]
        print(f"Saldo para {login}: ${saldo}")
    else:
        print(f"Usuário {login} não possui saldo registrado.")

# Função para definir novas credenciais
def definir_credenciais():
    login = input("Digite seu novo login: ")
    senha = input("Digite sua nova senha: ")

    # Atualizar as credenciais no arquivo
    with open('credenciais.json', 'w') as file:
        credenciais = {'login': login, 'senha': senha}
        json.dump(credenciais, file)

# Função para definir saldo para um usuário
def definir_saldo(login):
    saldo = float(input("Digite o saldo inicial: $"))
    # Carregar os saldos do arquivo
    try:
        with open('saldos.json', 'r') as file:
            saldos = json.load(file)
    except FileNotFoundError:
        saldos = {}

    # Atualizar ou adicionar o saldo do usuário
    saldos[login] = saldo
    with open('saldos.json', 'w') as file:
        json.dump(saldos, file)
    print(f"Saldo definido com sucesso para {login}: ${saldo}")

# Menu principal
def menu():
    print("Bem-vindo ao Sistema de Login e Conta Bancária!")
    print("1. Registrar/Login")
    print("2. Definir Novas Credenciais")
    print("3. Definir Saldo")
    print("4. Sair")

    opcao = input("Escolha uma opção: ")

    if opcao == '1':
        registrar_ou_logar()
    elif opcao == '2':
        definir_credenciais()
    elif opcao == '3':
        login = input("Digite o login do usuário: ")
        definir_saldo(login)
    elif opcao == '4':
        print("Saindo...")
    else:
        print("Opção inválida. Tente novamente.")
        menu()

# Executar o programa
if __name__ == "__main__":
    menu()
