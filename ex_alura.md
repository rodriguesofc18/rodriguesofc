import os

lista_numeros_media = []
lista_numeros = []
numeros = ""
for i in range(1,11):
    lista_numeros.append(int(i))
lista_nomes = ['thiago', 'debora', 'catharina', 'emanuela']
lista_ano = [1989, 2024]

# 1 - Crie uma lista para cada informação a seguir:
#     Lista de números de 1 a 10;
#     Lista com quatro nomes;
#     Lista com o ano que você nasceu e o ano atual.
def exercicio_1():
    numero_exercicio(1)
    print(lista_numeros)
    print(lista_nomes)
    print(lista_ano)
    separador_de_linha()

#2 - Crie uma lista e utilize um loop for para percorrer todos os elementos da lista.
def exercicio_2():
    numero_exercicio(2)
    for i in lista_numeros:
        print(i)
    separador_de_linha()

#3 - Utilize um loop for para calcular a soma dos números ímpares de 1 a 10.
def exercicio_3():
    numero_exercicio(3)
    soma = 0
    for i in lista_numeros:
        if i % 2 != 0:
            soma += i
    print(f'O valor da soma de números ímpares da lista é: {soma}')
    separador_de_linha()

#4 - Utilize um loop for para imprimir os números de 1 a 10 em ordem decrescente.
def exercicio_4():
    numero_exercicio(4)
    lista_numeros_reversa = reversed(lista_numeros)
    for i in lista_numeros_reversa:
        print(i)
    separador_de_linha()

#5 - Solicite ao usuário um número e, em seguida, utilize um loop for para imprimir a tabuada desse número, indo de 1 a 10.
def exercicio_5():
    numero_exercicio(5)
    try:
        numero_tabuada = int(input('Digite um número para saber a sua tabuada: \n'))
        for i in lista_numeros:
            tabuada = i * numero_tabuada
            print(f'{i} x {numero_tabuada} = {tabuada}')
    except:
        print(f'Você digitou {numero_tabuada}, digite um número válido.')
        exercicio_5()
    separador_de_linha()

#6 - Crie uma lista de números e utilize um loop for para calcular a soma de todos os elementos. 
#Utilize um bloco try-except para lidar com possíveis exceções.
def exercicio_6():
    numero_exercicio(6)
    soma = 0
    for i in lista_numeros:
        soma += i
    print(f'A soma de todos os valores da lista: {lista_numeros}\n é: {soma}')
    separador_de_linha()

#7 - Construa um código que calcule a média dos valores em uma lista. 
#Utilize um bloco try-except para lidar com a divisão por zero, caso a lista esteja vazia.
def exercicio_7():
    numero_exercicio(7)
    inserir_numero()

def inserir_numero():
    numeros = input('digite uma sequencia de numeros para fazer uma média ou uma letra para parar e sair: ')
    numeros = numeros.replace(',' , '.')
    try:
        try: 
            numero = int(numeros)
        except:
            numero = float(numeros)
        lista_numeros_media.append(numero)
        inserir_numero()
    except:
        media = round(sum(lista_numeros_media) / len(lista_numeros_media), 2)
        print(f'\nOs valores digitados são: {lista_numeros_media} \ne a média é: {media}')
        pergunta = input('Deseja finalizar (s/n)?')
        if pergunta == 's':
            os.system('cls')
        else:
            inserir_numero()

def numero_exercicio(texto):
    print(f'\nExercicio {texto}')

def separador_de_linha():
    print('-' * 20, '\n')

def finalizar():
    os.system('cls')

def opcao_invalida():
    print('Opção inválida')
    exibir_exercicio()

def exibir_exercicio():
    try:
        opcao_digitada = int(input('Digite o número do exercício de 1 a 7 ou "0" para sair: \n'))
        match opcao_digitada:
            case 1:
                exercicio_1()
                exibir_exercicio()
            case 2:
                exercicio_2()
                exibir_exercicio()
            case 3:
                exercicio_3()
                exibir_exercicio()
            case 4:
                exercicio_4()
                exibir_exercicio()
            case 5:
                exercicio_5()
                exibir_exercicio()
            case 6:
                exercicio_6()
                exibir_exercicio()
            case 7:
                exercicio_7()
                exibir_exercicio()
            case 0:
                finalizar()
            case _:
                opcao_invalida()
    except:
        opcao_invalida()

def opcao_invalida():
    print('Opção inválida')
    exibir_exercicio()

def main():
    exibir_exercicio()
    finalizar()

if __name__ == '__main__':
    main()
