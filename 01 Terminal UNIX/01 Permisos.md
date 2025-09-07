# Permissos dels arxius:

Els permisos d'arxius i usuaris a Unix són un mecanisme que regula qui pot accedir i modificar els fitxers i directoris del sistema. Cada fitxer o directori té associats tres tipus de permisos per a tres categories d'usuaris diferents.

## Categories d'usuaris

- **Propietari (user)**: l'usuari que ha creat l'arxiu o al qual se li ha assignat.

- **Grup (group)**: un conjunt d'usuaris als quals pertany el fitxer.

- **Altres (others)**: tots els altres usuaris del sistema que no són ni el propietari ni part del grup.

## Tipus de permisos

Cada fitxer o directori pot tenir tres tipus de permisos bàsics:

- **r (read)**: Permet llegir el contingut del fitxer o llistar el contingut del directori.

- **w (write)**: Permet modificar el fitxer o afegir/esborrar fitxers dins un directori.

- **x (execute)**: Permet executar el fitxer com un programa o accedir a un directori.

## Sintaxi dels permisos

- `u`: usuari

- `g`: grup

- `o`: altres (other)

- `+`: afegir permís

- `-`: treure permís

- `r`: permís de lectura

- `w`: permís d'escriptura

- `x`: permís d'execució

## Exemple per practicar:

La comanda **'ls -ltr'** mostra la llista d'arxius de la carpeta actual, i els seus permissos:

```bash
ls -ltr
```

Sortida:
```text
-rw-r--r--  1 nomusuari  staff   0 Sep  6 10:52 br.txt
-rw-r--r--  1 nomusuari  staff  15 Sep  6 10:55 hl1.txt
-rw-r--r--  1 nomusuari  staff  14 Sep  6 10:55 hl0.txt
-rw-r--r--  1 nomusuari  staff  15 Sep  6 11:02 nou-hl1.txt
drwxr-xr-x  3 nomusuari  staff  96 Sep  6 11:05 ghi
```

En aquest exemple, el propietari d'aquests arxius és 'nomusuari' i el grup al que pertany és 'staff'. Els permissos són:

- L'usuari pot llegir i escriure (rw)
- El grup pot llegir els arxius (r)
- Tothom pot llegir els arxius (r)

Per fer que només l'usuari i el seu grup tinguin accés a veure l'arxiu 'nou-hl1.txt':
```bash
chmod o-r nou-hl1.txt
```

**Nota**: A la comanda anterior la **o** significa **(others)**

Veure els permissos actuals de l'arxiu:
```bash
ls -ltr nou-hl1.txt
```

Sortida:
```
-rw-r-----  1 nomusuari  staff  15 Sep  6 11:02 nou-hl1.txt
```

**Nota**: Fixeu-vos que el tercer grup ara només té '---' el què vol dir que els altres no tenen cap permis, ni de lectura.

Si volem donar permisos d'escriptura al propi grup:
```bash
chmod g+rw nou-hl1.txt
```

Veure els permissos actuals de l'arxiu:
```bash
ls -ltr nou-hl1.txt
```

Sortida:
```
-rw-rw----  1 nomusuari  staff  15 Sep  6 11:02 nou-hl1.txt
```
# Execució de programes

Crea un arxiu **"arxiu.py"** amb el següent contingut
```python
#!/usr/bin/env python3

print("hola")
```
Dona-li permissos d'execució:
```bash
chmod u+x arxiu.py
```

Fes-lo anar amb **"./"**:
```bash
./arxiu.py
```



