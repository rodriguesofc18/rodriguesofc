#Solicite ao usuário que insira um número e, em seguida, use uma estrutura if else para determinar se o número é par ou ímpar.
#Prompt the user to enter a number and then use an if else structure to determine whether the number is even or odd.

def par_impar():
    numero = int(input('Digite um número: '))

    if numero % 2 == 0:
        print('Número par!')
    else:
        print('Número impar!')
