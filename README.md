# Apuntes-M03

# Col-lecions
https://docs.google.com/presentation/d/1VBIz16R1ChZ7JbKqK3LX2DqdHZke2gB-NtwSECcSEPM/edit#slide=id.p7

## List

- Una **List** es una colección **dinámica e indexada**.
- Los elementos se acceden mediante un **índice entero**.
- Mantiene el **orden de inserción** de los elementos.
- **Permite elementos duplicados**.

## Set

- Un **Set** es una colección **dinámica de elementos únicos**.
- Refleja la abstracción matemática del conjunto: **no permite duplicados**.
- El **orden de los elementos no está garantizado**.
- Ejemplo de uso: **cartas de una baraja española**.

## Map

- Un **Map** (o **diccionario**) es una colección **clave-valor**.
- Las **claves son únicas**, cada clave se relaciona con un **valor único**.
- Los **valores pueden estar repetidos**.
- Útil para representar conexiones lógicas entre objetos.
- Ejemplos de uso:
  - `{email : password}`
  - `{palabra : definición}`


# Excepcions

# Fitxers

https://github.com/ITEC-BCN/m3-a51-mario-kart-binari-maury-l1/blob/main/src/controllers/CharacteMarioKartController.kt

Se crea la carpeta al mismo nivel del src
## Importar datos:
   fun importarPersonatges() {
        if(!this.file.exists() || this.file.length() == 0L){
            this.llistaPersonatges = crearPersonatges()
            println("No hay nada disponible para importar.")
            println("Creando personajes default.")
        } else {
            ObjectInputStream(FileInputStream(file)).use { ois ->
                this.llistaPersonatges = ois.readObject() as MutableList<CharacterMarioKart>
            }
            println("Lista de personajes importada correctamente")
        }
    }
## Exportar datos: 
    fun exportarPersonatges() {
        ObjectOutputStream(FileOutputStream(file)).use { oos ->
            oos.writeObject(llistaPersonatges)
        }
        println("Lista de personajes exportada correctamente.")
    }

# Interficies Graficas

# Regex

# Generix
