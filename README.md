# Gerador-de-senhas# Gerador de Senhas
import random
import string

def gerar_senha(comprimento=12, incluir_maiusculas=True, incluir_numeros=True, incluir_simbolos=True):
    # Definindo os caracteres básicos
    caracteres = string.ascii_lowercase  # Letras minúsculas
    
    if incluir_maiusculas:
        caracteres += string.ascii_uppercase  # Adiciona letras maiúsculas
    if incluir_numeros:
        caracteres += string.digits  # Adiciona números
    if incluir_simbolos:
        caracteres += string.punctuation  # Adiciona símbolos

    # Gera a senha
    senha = ''.join(random.choice(caracteres) for _ in range(comprimento))
    return senha

# Interação com o usuário
def main():
    print("Gerador de Senhas")
    comprimento = int(input("Digite o comprimento da senha (padrão 12): ") or 12)
    
    incluir_maiusculas = input("Incluir letras maiúsculas? (s/n): ").lower() == 's'
    incluir_numeros = input("Incluir números? (s/n): ").lower() == 's'
    incluir_simbolos = input("Incluir símbolos? (s/n): ").lower() == 's'

    senha = gerar_senha(comprimento, incluir_maiusculas, incluir_numeros, incluir_simbolos)
    print(f"Sua senha gerada é: {senha}")

if __name__ == "__main__":
    main()
