# Astracción 
____________________________________________________________________________________________
 
La abstracción es el proceso de identificar y enfocarse en los aspectos más importantes de un sistema, dejando de lado los detalles que no son relevantes. Este principio nos permite representar elementos del mundo real como entidades en el código, lo que hace que sea más fácil entender y trabajar con el sistema.
____________________________________________________________________________________________
## Ejemplo en el proyecto 

## Imagen que describe
![image](https://github.com/user-attachments/assets/57a19514-1f6a-4d98-b88f-64096f1c51b6)

____________________________________________________________________________________________
[Diagrama de las clases](https://docs.google.com/presentation/d/1hRUJWvK62TNMjvtD5F0mrpfBQo8xms379FoKEji9zoo/edit#slide=id.p) 
____________________________________________________________________________________________
## Ejemplo de Código 

// Clase abstracta Usuario
public abstract class Usuario {
    protected String nombre;  // Atributo común para todos los usuarios

    // Constructor que inicializa el nombre del usuario
    public Usuario(String nombre) {
        this.nombre = nombre;
    }

    // Método abstracto, debe ser implementado por las subclases
    public abstract String obtenerInformacion();
}

// Subclase Bibliotecario que extiende Usuario
public class Bibliotecario extends Usuario {
    private int idBibliotecario;  // Atributo específico del bibliotecario

    // Constructor de la subclase Bibliotecario
    public Bibliotecario(String nombre, int idBibliotecario) {
        super(nombre);  // Llama al constructor de la clase base (Usuario)
        this.idBibliotecario = idBibliotecario;
    }

    // Implementación del método abstracto obtenerInformacion
    @Override
    public String obtenerInformacion() {
        // Devuelve información específica del bibliotecario
        return "Bibliotecario: " + nombre + " - ID: " + idBibliotecario;
    }
}


____________________________________________________________________________________________
## ¿Cómo se aplica la abstracción?

La clase Usuario proporciona una interfaz común: el método obtenerInformacion(), que todos los tipos de usuarios (como Bibliotecario y Estudiante) deben implementar. Esto permite que el código cliente (como el método main()) interactúe con objetos de tipo Usuario sin preocuparse por los detalles de implementación de cada tipo específico de usuario.

Los detalles de implementación están ocultos en las subclases: La forma en que se obtiene la información de un Bibliotecario o un Estudiante es diferente y está encapsulada dentro de cada subclase. El cliente solo interactúa con la interfaz común definida en Usuario, sin necesidad de saber cómo funciona internamente cada tipo de usuario.

Este es un ejemplo de abstracción, donde solo se expone la interfaz necesaria (obtenerInformacion()), mientras que los detalles de cómo cada tipo de usuario implementa esa interfaz se ocultan en las subclases concretas.
