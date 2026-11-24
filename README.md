# Bit Survivors

Ein Vampire-Survivors-Like in C++ und OpenGL. Trainingsprojekt.
## Lokaler Befehl `runbs`

`runbs` baut das Spiel und startet es. Der Befehl gilt nur auf dem eigenen Rechner und steht deshalb nicht in `dotfiles`, sondern in `~/.zshrc.local`.

Einmalig den Ordner `build/` einrichten:

```bash
cd ~/codeforge/github/lokthok/bit-survivors
cmake -S . -B build
```

Den Befehl unten an `~/.zshrc.local` anhängen und laden:

```bash
echo "alias runbs='cmake --build ~/codeforge/github/lokthok/bit-survivors/build && ~/codeforge/github/lokthok/bit-survivors/build/game'" >> ~/.zshrc.local
source ~/.zshrc.local
```
