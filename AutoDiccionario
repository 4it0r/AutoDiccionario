import itertools
import time

def toggle_case(word):
    if word.isalpha():  # Comprueba si la palabra contiene solo letras
        return "".join(x.upper() if x.islower() else x.lower() for x in word)
    return word  # Devuelve la palabra original si contiene números

def generate_combinations(words):
    print("Creando diccionario con su combinación de palabras...")
    all_combinations = []
    for L in range(1, len(words) + 1):
        for subset in itertools.permutations(words, L):
            all_combinations.append("".join(subset))
            for i in range(len(subset)):
                temp = list(subset)
                temp[i] = toggle_case(subset[i])
                all_combinations.append("".join(temp))
    return all_combinations

def write_to_file(filename, combinations):
    with open(filename, 'w') as f:
        for item in combinations:
            f.write(f"{item}\n")

if __name__ == "__main__":
    all_words = []
    total_count = 0
    while True:
        user_input = input("Introduce las palabras y números separados por espacios: ")
        words = user_input.split()
        all_words.extend(words)
        combinations = generate_combinations(all_words)
        write_to_file("combinaciones.txt", combinations)
        
        total_count += len(combinations)
        print(f"Diccionario actualizado con {total_count} palabras.")
        
        another_round = input("¿Quieres añadir más palabras o números? (s/n): ")
        if another_round.lower() == 'n':
            print("Apagando el script...")
            time.sleep(3)  # Espera 3 segundos
            break
