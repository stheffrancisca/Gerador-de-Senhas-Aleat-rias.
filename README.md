# Gerador-de-Senhas-Aleat-rias.
Gerador de Senhas Aleatórias.
### Este programa permite ao usuário gerar senhas aleatórias que atendem a requisitos específicos de segurança. O usuário define o comprimento desejado da senha, e o programa garante que a senha gerada contenha pelo menos uma letra, um número e um caractere especial. Senhas geradas não contêm espaços em branco.

### Funcionalidades
Comprimento Personalizável: O usuário pode definir o comprimento da senha. Se o comprimento informado for menor que 4, o programa solicita um novo valor.
Senha Segura: As senhas geradas incluem obrigatoriamente letras, números e caracteres especiais.
Geração Aleatória: Cada vez que o programa é executado, uma nova senha é gerada.
Função gerar_senha: Esta função recebe o comprimento da senha como parâmetro e retorna a senha gerada. Se o comprimento for inválido, a função retorna None.

###Dicas
Utilize a biblioteca random para embaralhar os caracteres da senha.
A função shuffle da biblioteca random pode ser útil para misturar os caracteres.
A função choice da biblioteca random pode ser utilizada para selecionar caracteres aleatórios.
A biblioteca string fornece listas úteis de caracteres válidos para a senha. ####

###Documentação:

- https://docs.python.org/pt-br/3/library/string.html
- https://docs.python.org/pt-br/3/library/random.html#functions-for-sequences



import string
import random


def gerar_senha(tamanho):
    if tamanho < 4:
        print("O tamanho da senha deve ser de pelo menos 4")
    
    else: 
        senha = [
            random.choice(string.ascii_letters),
            random.choice(string.digits),
            random.choice(string.punctuation)
        ]
 
        possibilidades = ''.join([string.ascii_letters, string.digits, string.punctuation])
        senha.extend(random.choices(possibilidades, k=tamanho-3))

        random.shuffle(senha)
        return ''.join(senha)


tamanho = int(input("Digite o comprimento da senha: "))
print(gerar_senha(tamanho))
