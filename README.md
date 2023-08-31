# Aula2-3

#Aula 03 
#Exemplo 1
arquivo = open("Crescente.txt", "w")
for numeros in range(1,101):
   arquivo.write(str(numeros) + ',')
   print(numeros,end=";")
arquivo.close()

#Exemplo 2
 def registrar_nota(aluno, nota):
    with open('notas.txt', 'a') as arquivo:
        arquivo.write(f'{aluno}: {nota}\n')

def ler_notas():
    try:
        with open('notas.txt', 'r') as arquivo:
            notas = arquivo.readlines()
            for nota in notas:
                print(nota.strip())
    except FileNotFoundError:
        print("Nenhum dado encontrado.")

while True:
    print("1. Registrar nota")
    print("2. Ler notas")
    print("3. Sair")
    opcao = input("Escolha uma opção: ")

    if opcao == '1':
        aluno = input("Nome do aluno: ")
        nota = input("Nota do aluno: ")
        registrar_nota(aluno, nota)
    elif opcao == '2':
        ler_notas()
    elif opcao == '3':
        break
    else:
        print("Opção inválida. Escolha novamente.")
