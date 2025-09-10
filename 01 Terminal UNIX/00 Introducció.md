
**Nota:**[Tutoral instal·lació](https://github.com/optimisme/DAM-LlenguatgeMarques/blob/main/00-Instal·lació/Teoria.md) 

# Terminal

El terminal permet accedir i gestionar a l'ordinador a partir de comandes.

Per accedir al terminal:

- **Windows**: PowerShell, CMD, o WSL (Windows Subsystem for Linux).
- **Linux**: Bash, terminal predeterminat del sistema.
- **macOS**: Aplicació "Terminal" (bash o zsh per defecte).

## Terminal UNIX

Aquesta introducció està pensada per terminals UNIX, així que cal un terminal Linux, macOS o bé en cas de Windows un terminal WSL.

Enlloc d'accedir gràficament a les carpetes i arxius de l'ordinador, el terminal permet fer-ho en mode text.

La carpeta principal de l'usuari es diu **'HOME'** i s'hi accedeix a través del símbol **'~'**

```bash
cd ~
```

La comanda **'cd'** vol dir **'change directory'**, en l'exemple anterior 'change to directory HOME'

Per llistar els continguts d'una carpeta es pot fer servir la comanda **'ls' (list)**:

```bash
ls
```

Així, si una de les carpetes llistades per la comanda anterior es diu 'Documents', podem entrar-hi amb:

```bash
cd Documents
```

Per saber a quina carpeta ens trobem, hi ha la comanda **'pwd' (print working directory)**

```bash
pwd
```

L'exemple anterior mostrarà la ruta des de la que s'ha cridat la comanda:

```text
/Users/username/Documents
```

Aquesta és la llista de comandes bàsiques:

- **Navegació pel sistema de fitxers**:

    `pwd`: mostra el directori actual

    `tree`: mostra l'estructura de carpetes

    `ls`: llistar els fitxers i directoris

    `cd`: canviar de directori

    `mkdir`: crear un directori

    `rmdir`: esborrar una carpeta buida

    `rm -rf`: esborrar una carpeta i els seus continguts

- **Carpetes principals**:

    `/`: arrel del sistema

    `~`: carpeta arrel de l'usuari

    `.`: carpeta actual

    `..`: carpeta pare de la carpeta actual

- **Gestió de fitxers**:

    `touch`: crear fitxers

    `cp`: copiar fitxers

    `mv`: moure o renombrar fitxers

    `rm`: esborrar fitxers

    `grep`: buscar textos dins d'arxius

    `find`: buscar arxius o carpetes

- **Permisos i usuaris**:

    `ls -ltr`: veure permissos dels arxius

    `chmod`: canviar permissos dels arxius

    `sudo`: canviar d'usuari

- **Processos**:

    `ps`, `top`: visualitzar processos

    `kill`: tancar processos

- **Gestió de paquets**:

    `sudo apt update`: descarregar llista d'actualitzacions

    `sudo apt upgrade`: actualitzar el sistema

    `sudo apt install`: instal·lar un nou paquet

- **Cerca i filtres**:

    `grep`: cerca patrons dins de fitxers

    `find`: cerca fitxers i carpetes

- **Terminal**:

    `clear`: neteja la consola

    `reset`: reinicia la consola

- **Continguts**:

    `more`: mostrar continguts d'un arxiu

    `tail`: mostrar el final d'un arxiu

## Exemple per practicar:

Crear la carpeta 'abc':
```bash
mkdir abc
```
Entrar dins la carpeta 'abc':
```bash
cd abc
```
Tornar a la carpeta anterior a 'abc':
```bash
cd ..
```
Mostrar la carpeta on estem:
```bash
pwd
```
Entrar dins la carpeta 'abc':
```bash
cd abc
```
Mostrar la carpeta on estem:
```bash
pwd
```
Llistar els cotinguts de la carpeta:
```bash
ls
```
Crear un arxiu buit anomenat 'ar0.txt':
```bash
touch ar0.txt
```
Crear l'arxiu 'hl0.txt' amb el texto "hola":
```bash
echo "hola" > hl0.txt
```
Afegir 'què tal?' a l'arxiu 'hl0.txt':
```bash
echo "què tal" >> hl0.txt
```
Mostrar els continguts de l'arxiu 'hl0.txt':
```bash
more hl0.txt
```
Afegir 'hola,\ntot bé?' a l'arxiu 'hl1.txt':
```bash
echo "hola,\ntot bé?" > hl1.txt
```
**Nota:** Fixeu-vos que '\n' és un salt de línia.

Mostrar els continguts de l'arxiu 'hl1.txt':
```bash
more hl1.txt
```
Mostrar tots els arxius que contenen la paraula 'hola':
```bash
grep "hola" *
```
**Nota:** Fixeu-vos que '*' significa 'tots'.

Llistar tots els arxius que tenen un '1' al seu nom:
```bash
ls *1*
```

Llistar tots els arxius amb extensió '.txt':
```bash
ls *.txt
```

Llistar tots els arxius que el seu nom comença per 'hl':
```bash
ls hl*
```

Canviar el nom de l'arxiu 'ar0.txt' per 'br.txt'
```bash
mv ar0.txt br.txt
```

Copiar l'arxiu 'hl1.txt' a un nou arxiu:
```bash
cp hl1.txt nou-hl1.txt
```

Llistar tots els arxius tenen 'hl' al seu nom:
```bash
ls *hl*
```

Crear la carpeta 'def':
```bash
mkdir def
```

Crear la carpeta 'ghi' i a dins seu, la carpeta 'jkl':
```bash
mkdir -p ghi/jkl
```

Crear l'arxiu 'nono' dins la carpeta 'def' i l'arxiu 'sisi.txt' dins la carpeta 'jkl':
```bash
touch def/nono
echo "Mono" > ghi/jkl/sisi.txt
```

**Nota**: Fixeu-vos que els arxius no tenen perquè tenir una extensió tipus '.txt'

Veure l'estructura d'arxius i carpetes actual:
```bash
tree .
```

Hauria de mostrar:
```text
.
├── br.txt
├── def
│   └── nono
├── ghi
│   └── jkl
│       └── sisi.txt
├── hl0.txt
├── hl1.txt
└── nou-hl1.txt
```

Esborra la carpeta 'def' i tots els seus continguts:
```bash
rm -rf def
```

Veure l'estructura d'arxius i carpetes actual:
```bash
tree .
```

Veure l'estructura d'arxius i carpetes actual:
```bash
tree .
```

Hauria de mostrar:
```text
.
├── br.txt
├── ghi
│   └── jkl
│       └── sisi.txt
├── hl0.txt
├── hl1.txt
└── nou-hl1.txt
```

Veure l'estructura d'arxius i carpetes actual:
```bash
tree . -L 2
```

Hauria de mostrar:
```text
.
├── br.txt
├── ghi
│   └── jkl
├── hl0.txt
├── hl1.txt
└── nou-hl1.txt
```

Buscar tots els arxius de text que tenen la paraula "mono" dins:
```bash
grep -ri "mono" .
```

**Nota**: La comanda anterior busca dins de carpetes i subcarpetes de manera recursiva **(r)**, i no té en compte majúscules o minúsculles **(i)**

Buscar tots els fitxers i carpetes dins la carpeta actual
```bash
find .
```

Buscar només fitxers amb extensió .txt
```bash
find . -name "*.txt"
```

Buscar només carpetes
```bash
find . -type d
```

Buscar subcarpetes limitant la cerca a 2 nivells
```bash
find . -maxdepth 2 -type d
```

Hauria de mostrar
```bash
.
./ghi
./ghi/jkl
```

Combinar 'find' amb 'grep'
```bash
find . -name "*.txt" -exec grep -l "mono" {} +
```