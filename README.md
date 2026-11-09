# Teste

N, n = map(int, input().split())
faixas = list(map(int, input().split()))

melhor = 0

def buscar(i, soma):

    global melhor

    if soma > N:
        return

    melhor = max(melhor, soma)

    if i == n:
        return

    buscar(i + 1, soma + faixas[i])
    buscar(i + 1, soma)


buscar(0, 0)

print(melhor)
