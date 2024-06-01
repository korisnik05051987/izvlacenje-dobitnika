# Draw a Random Winner

Ovaj projekt omogućava nasumično izvlačenje jednog dobitnika iz liste učesnika koja se nalazi u fajlu `participants.txt`. Svaki put kada se pokrene program, izvučeni dobitnik se uklanja iz liste, a preostali učesnici se ažuriraju u fajlu.

## Potrebne komponente

- Python 3.x

## Priprema

1. Kreirajte fajl `participants.txt` u istom direktorijumu gde se nalazi Python skripta.
2. Dodajte imena učesnika u `participants.txt`, jedno ime po liniji. Na primer:

    ```
    Alice
    Bob
    Charlie
    Diana
    Eve
    ```

## Korišćenje

1. Pokrenite Python skriptu:

    ```bash
    python draw_winner.py
    ```

2. Skripta će nasumično izvući jednog dobitnika iz `participants.txt` i prikazati njegovo ime.

3. Nakon izvlačenja, izvučeni dobitnik će biti uklonjen iz `participants.txt`, tako da neće biti izvučen ponovo pri sledećem pokretanju skripte.

## Kod

```python
import random

# Učitavanje učesnika iz fajla
with open('participants.txt', 'r') as file:
    participants = file.read().splitlines()

# Nasumično izvlačenje jednog učesnika
winner = random.choice(participants)
print(f"The winner is: {winner}")

# Ažuriranje fajla sa preostalim učesnicima
participants.remove(winner)
with open('participants.txt', 'w') as file:
    file.write('\n'.join(participants))
