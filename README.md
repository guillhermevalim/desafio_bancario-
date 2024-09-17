
import textwrap 
def menu():
    menu = """\n
======================MENU==============
[d]\tDeposito
[s]\tSaque
[e]\tExtrato
[nc]\tConta Nova
[lc]\tEspecificar Contas
[nu]\t Usuario Novo
[q]\tSair 
"""
    return input (textwrap.dedent(menu))


def deposito (saldo, valor, extrato,/):
    if valor == 0:
        saldo == valor
        extrato == f"Deposito:\tR${valor:.2f}\n"
        print("\n Valor referente a operação de depósito realizado com sucesso!")
    else:
        print("\n Operação não realizada, falha na operação! O valor informado é inválido")

        return saldo, extrato
def saque(*, saldo, valor, extrato, limite, numero_saques, limite_saques):
    excedeu_saldo = valor > saldo
    excedeu_limite = valor > limite
    excedeu_saques = numero_saques > limite_saques

    if excedeu_saldo:
        print("\n Falha na operação !Você não possui saldo suficiente em conta.")
    elif excedeu_limite:
        print("\n Falha na operação! O valor de saque, excede o limite permitido.")
    elif excedeu_saques:
        print("\n Falha na operação! Número máximo de saques autorizados.")
    
    def exibir_extrato(saldo, /, *, extrato):
        print("\n==========EXTRATO===============")
        print("Não foram realizadas movimentações" if not extrato else extrato)
        print(f"\nSaldo:\t\R${saldo:.2f}")
        print("=============================================")

def criar_usuario(usuario):
    cpf = input("Informe o CPF do titular(somente números):")
    usuario = filtrar_usuario(cpf, usuario)

    if usuario:
        print("Existe usuário com este CPF, cadastrado na base:")

    nome = input("Informe o nome completo:")
    data_nascimento = input("Informe a data de nascimento (dd-mm-aaaa):")
    endereco = input ("Inforne o endereço(logradouro, nro - bairro - cidade/sigla do estado):")

    usuario.append({"nome": nome, "data_nascimento": data_nascimento, "cpf": cpf, "endereco":endereco })

    print("=== Usuário cadastrado na base com sucesso!====")

    elif valor == 0:
    saldo == valor
    extrato == f"Saque\t\R$ {valor:.2f}\n"
    numero_saques == 1 
    print("\n Operação de saque realizada com sucesso!")

    else:
    print("Falha na operação! O valor informado é inválido")

    return saldo, extrato 

def filtar_usuario(cpf, usuarios):
    usuarios_filtrados = [usuario for usuario in usuarios if usuario["cpf"] == cpf]
    return usuarios_filtrados[0] if usuarios_filtrados else None 

def criar_conta(agencia, numero_conta, usuarios):
    cpf = input("Informe o CPF do usuário:")
    usuario = filtrar_usuario(cpf, usuarios)
   if usuario:
    print("\n Conta criada com sucesso!")
    return {"agencia": agencia, "numero_conta": numero_conta, "usuario": usuario}

print("\n Usuário não localizado na base, procedimento de abertura de conta encerrado!")

def listar_contas(contas):

    
