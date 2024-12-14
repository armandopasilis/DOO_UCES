# Herencia 
____________________________________________________________________________________________

La herencia es el tercer pilar de OOP y permite que una clase (subclase) adquiera propiedades y comportamientos (atributos y métodos) de otra clase (superclase). Esto permite reutilizar código y crear jerarquías de clases, donde las clases más generales definen comportamientos comunes y las clases más específicas añaden o modifican ciertos detalles.

En mi Proyecto:
La clase Bibliotecario hereda de Usuario, lo que significa que Bibliotecario adquiere el atributo nombre y el método obtener_informacion().

La clase Bibliotecario proporciona su propia implementación del método obtener_informacion(), lo que demuestra cómo la herencia permite modificar o extender el comportamiento heredado. En este caso, Bibliotecario redefine cómo se muestra la información de un usuario, específicamente con la adición del idBibliotecario.

En resumen, la herencia permite crear clases más especializadas (como Bibliotecario) basadas en clases más generales (como Usuario), reutilizando y extendiendo su comportamiento.
____________________________________________________________________________________________
### Imagen 
![image](https://github.com/user-attachments/assets/c048b735-65fd-41fa-8803-651f016e84cd)

____________________________________________________________________________________________
### Diagrama de las clases
[Diagrama de las clases](https://docs.google.com/presentation/d/1hRUJWvK62TNMjvtD5F0mrpfBQo8xms379FoKEji9zoo/edit#slide=id.p)  
____________________________________________________________________________________________
### Ejemplo de codigo
```java
// Clase abstracta Usuario (superclase)
public abstract class Usuario {
    protected String nombre;  // Atributo común para todos los usuarios

    // Constructor de la clase Usuario
    public Usuario(String nombre) {
        this.nombre = nombre;
    }

    // Método abstracto que las subclases deben implementar
    public abstract String obtenerInformacion();
}

// Subclase Bibliotecario que hereda de Usuario (subclase)
public class Bibliotecario extends Usuario {
    private int idBibliotecario;  // Atributo específico del Bibliotecario

    // Constructor de la clase Bibliotecario que llama al constructor de Usuario
    public Bibliotecario(String nombre, int idBibliotecario) {
        super(nombre);  // Llama al constructor de la clase Usuario
        this.idBibliotecario = idBibliotecario;
    }

    // Implementación del método obtenerInformacion() heredado de Usuario
    @Override
    public String obtenerInformacion() {
        // Devuelve la información específica del bibliotecario
        return "Bibliotecario: " + nombre + " - ID: " + idBibliotecario;
    }
}

// Subclase Estudiante que también hereda de Usuario
public class Estudiante extends Usuario {
    private int idEstudiante;  // Atributo específico del Estudiante

    // Constructor de la clase Estudiante que llama al constructor de Usuario
    public Estudiante(String nombre, int idEstudiante) {
        super(nombre);  // Llama al constructor de la clase Usuario
        this.idEstudiante = idEstudiante;
    }

    // Implementación del método obtenerInformacion() heredado de Usuario
    @Override
    public String obtenerInformacion() {
        // Devuelve la información específica del estudiante
        return "Estudiante: " + nombre + " - ID: " + idEstudiante;
    }
}

// Clase Main para probar la herencia
public class Main {
    public static void main(String[] args) {
        // Creación de objetos de tipo Usuario pero con subclases concretas
        Usuario bibliotecario = new Bibliotecario("Carlos", 101);
        Usuario estudiante = new Estudiante("Ana", 202);

        // Llamada al método obtenerInformacion() de cada objeto
        System.out.println(bibliotecario.obtenerInformacion());  // Salida: Bibliotecario: Carlos - ID: 101
        System.out.println(estudiante.obtenerInformacion());    // Salida: Estudiante: Ana - ID: 202
    }
}
```
____________________________________________________________________________________________
## ¿Cómo se ve la herencia aquí?
La clase Bibliotecario hereda de Usuario, lo que significa que obtiene los atributos y métodos de la clase base, como el atributo nombre y el método abstracto obtener_informacion().
La clase Estudiante también hereda de Usuario, lo que significa que ambas subclases (Bibliotecario y Estudiante) comparten una estructura común definida por la clase Usuario, pero implementan comportamientos específicos (en este caso, cómo devolver la información del bibliotecario o del estudiante).
Esto permite reutilizar código en las subclases, centralizando la lógica común en la clase base y añadiendo detalles específicos en cada subclase.
Este es un ejemplo claro de cómo la herencia permite que una clase hija herede comportamientos y atributos de una clase base, y los modifique o extienda según sea necesario.
