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
----
n, capacidade = map(int, input().split())

caixas = []

for i in range(n):
    qtd, unidades = map(int, input().split())
    caixas.append((unidades, qtd))

# Ordenar da maior para a menor quantidade de unidades
caixas.sort(reverse=True)

total = 0

for unidades, qtd in caixas:

    pegar = min(qtd, capacidade)

    total += pegar * unidades

    capacidade -= pegar

    if capacidade == 0:
        break

print(total)
