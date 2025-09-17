# trial-2
i dont know how to solve this problem
import math

def distance(pokemon, shot):
    return math.sqrt((pokemon['x'] - shot['x'])**2 + (pokemon['y'] - shot['y'])**2)
def match_shots(pokemons, shots, radius):
    matched = {}
    used_pokemons = set()
    
    for shot in shots:
        for pokemon in pokemons:
            if pokemon['id'] in used_pokemons:
                continue
            if distance(pokemon, shot) <= radius:
                matched[pokemon['id']] = shot
                used_pokemons.add(pokemon['id'])
                break
    return matched
import matplotlib.pyplot as plt

for p in pokemons:
    plt.plot(p['x'], p['y'], 'ro')  # Pokémon in red
for s in shots:
    plt.plot(s['x'], s['y'], 'bo')  # Shots in blue
plt.show()
