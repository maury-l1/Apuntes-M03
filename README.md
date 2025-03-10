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

  https://github.com/ITEC-BCN/kotlin-test-files-exceptions/tree/main/src
  https://docs.google.com/presentation/d/1vpd1UyVY2D268b8p_0SpfEz1ckdUgtyEQ6QN7RBrMiE/edit#slide=id.g2ba554a52e1_0_193
  ![image](https://github.com/user-attachments/assets/c62e225f-5f34-4661-8a99-d9b8aeb3170d)

- Se pueden crear excepciones personalizadas para posibles errores en contextos especificos
- Se pueden usar excepciones predeterminadas como IOE, AritmethicException

  Excepcion personalizada ejemplo:

            // Definición de la clase con un constructor secundario sin parámetros
          class EdadInvalidaException : Exception {
              // Constructor secundario sin parámetros
              constructor() : super("La edad no puede ser negativa")  // Mensaje predeterminado
          
              // Constructor con un parámetro para pasar un mensaje personalizado
              constructor(message: String) : super(message)
          }
  
  
                 // Función para validar la edad
      fun validarEdad(edad: Int) {
          if (edad < 0) {
              // Lanzar la excepción con el constructor sin parámetros (mensaje predeterminado)
              throw EdadInvalidaException()
          } else {
              println("Edad válida: $edad")
          }
      }
          
      fun main() {
          try {
              validarEdad(-5)  // Intentamos pasar una edad inválida
          } catch (e: EdadInvalidaException) {
              println("Error capturado: ${e.message}")  // Captura la excepción y muestra el mensaje
          }
          
          try {
              validarEdad(25)  // Ahora una edad válida
          } catch (e: EdadInvalidaException) {
              println("Error capturado: ${e.message}")  // No se lanzará ninguna excepción aquí
          }
}
# Fitxers

https://github.com/ITEC-BCN/m3-a51-mario-kart-binari-maury-l1/blob/main/src/controllers/CharacteMarioKartController.kt

Se crea la carpeta al mismo nivel del src

## Crear carpeta: 
    fun crearFitxer() {
    
            if(!this.carpeta.exists()) {
                this.carpeta.mkdirs()
            }
    
            if(!this.file.exists()) {
                this.file.createNewFile()
            }
        }

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

https://docs.google.com/presentation/d/1OdLI1epoWpJ7sGjd3wXxzugtFci-W8CmhXxR_E8igO8/edit#slide=id.g33a1bcdf32d_0_61

# Regex
https://github.com/ITEC-BCN/kotlin-demo-regex/blob/main/src/controllers/RegexController.kt
https://docs.google.com/presentation/d/1J_nwKATlYPjYkN_Rm5S07xGvi-0CWTv_P3EvJzUAELM/edit#slide=id.g339b7146eac_0_0



## 1. Primera letra mayúscula y resto minúscula

val regex = "^[A-Z][a-z]*$"

## 2. Solo entre 'a' y 'd' (inclusive)

val regex = "^[a-d]+$"

## 3. Medida limitada (mínimo 3 y máximo 5 caracteres)

val regex = "^.{3,5}$"

## 4. Permitir dígitos (solo números)

val regex = "^[0-9]+$"

## 5. Permitir solo dígitos con un límite de 3 dígitos (máximo 3 dígitos)

val regex = "^[0-9]{1,3}$"

## 6. Uso de \\d para dígitos (entre 2 y 4 dígitos)

val regex = "^\\d{2,4}$"

## 7. No puede ser ni b ni c

[a-e&&[^bc]]

### Explicación:

- `^`: Marca el inicio de la cadena.
- `$`: Marca el final de la cadena.
- `[a-d]`: Define un rango de caracteres, en este caso entre 'a' y 'd'.
- `+`: Uno o más caracteres que coincidan con la expresión anterior.
- `*`: Cero o más caracteres.
- `{min,max}`: Número de repeticiones entre un rango.
- `\\d`: Equivalente a `[0-9]`, representa un dígito.


# Generic

https://docs.google.com/presentation/d/15w4RGY6cOEL0uIkxEUDOJ0dT-_yk_TlrRh-829iAaY0/edit#slide=id.p1
