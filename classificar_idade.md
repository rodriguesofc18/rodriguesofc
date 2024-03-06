#Pergunte ao usuário sua idade e, com base nisso, use uma estrutura if elif else para classificar a idade em categorias de acordo com as seguintes condições:
#Ask the user their age and based on that, use an if elif else structure to sort the age into categories according to the following conditions:

def idade():
    idade = int(input('Qual sua idade? '))
    if idade <= 12 :
        print('Criança')
    elif 12 < idade <= 17 :
        print('Adolescente')
    elif idade > 17:
        print('Adulto')
    else:
        print('Idade inválida')
