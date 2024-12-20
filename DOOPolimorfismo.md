# Polimorfismo 
____________________________________________________________________________________________

El polimorfismo es el cuarto pilar de OOP y permite que se pueda usar un mismo método o clase de diferentes maneras.El polimorfismo permite que un objeto se comporte de diferentes formas dependiendo de su tipo real, aunque se esté utilizando como si fuera de un tipo más general.


## Ejemplo en el proyecto 

## Imagen que describe
![image](https://github.com/user-attachments/assets/683b7423-479a-4053-8086-377bb95b6a35)

____________________________________________________________________________________________
[Diagrama de las clases](https://docs.google.com/presentation/d/1hRUJWvK62TNMjvtD5F0mrpfBQo8xms379FoKEji9zoo/edit#slide=id.p) 
____________________________________________________________________________________________
## Ejemplo de Código 
```java
// Clase abstracta Usuario
public abstract class Usuario {
    protected String nombre;

    // Constructor de la clase Usuario
    public Usuario(String nombre) {
        this.nombre = nombre;
    }

    // Método abstracto que las subclases deben implementar
    public abstract String obtener_informacion();
}

// Subclase Bibliotecario que hereda de Usuario
public class Bibliotecario extends Usuario {
    private int idBibliotecario;

    // Constructor de la clase Bibliotecario
    public Bibliotecario(String nombre, int idBibliotecario) {
        super(nombre);  // Llama al constructor de Usuario
        this.idBibliotecario = idBibliotecario;
    }

    // Implementación del método obtenerInformacion()
    @Override
    public String obtener_informacion() {
        return "Bibliotecario: " + nombre + " - ID: " + idBibliotecario;
    }
}

// Subclase Estudiante que hereda de Usuario
public class Estudiante extends Usuario {
    private int idEstudiante;

    // Constructor de la clase Estudiante
    public Estudiante(String nombre, int idEstudiante) {
        super(nombre);  // Llama al constructor de Usuario
        this.idEstudiante = idEstudiante;
    }

    // Implementación del método obtenerInformacion()
    @Override
    public String obtener_informacion() {
        return "Estudiante: " + nombre + " - ID: " + idEstudiante;
    }
}

// Clase principal para demostrar el polimorfismo
public class Main {
    public static void main(String[] args) {
        // Creamos un array de objetos Usuario, pero pueden ser de cualquier tipo de subclase de Usuario
        Usuario[] usuarios = new Usuario[2];
        
        // Creamos un Bibliotecario y un Estudiante
        usuarios[0] = new Bibliotecario("Carlos", 101);
        usuarios[1] = new Estudiante("Ana", 202);
        
        // Utilizamos polimorfismo para llamar a obtener_informacion() en ambos objetos
        // El método correcto se ejecutará según el tipo real del objeto (Bibliotecario o Estudiante)
        for (Usuario usuario : usuarios) {
            System.out.println(usuario.obtener_informacion());  // Llamada polimórfica
        }
    }
}

```
____________________________________________________________________________________________
## ¿Cómo funciona el polimorfismo aquí?  
Polimorfismo de métodos: El método obtener_informacion() se invoca de manera polimórfica sobre cada objeto del array usuarios. Aunque el tipo de referencia es Usuario, el método que se ejecuta depende del tipo real del objeto (es decir, si es un Bibliotecario o un Estudiante).

Comportamiento dinámico: El comportamiento del método obtener_informacion() es dinámico y cambia según el tipo real del objeto en tiempo de ejecución. Este comportamiento es conocido como "vinculación tardía" o "late binding".

Este ejemplo ilustra cómo el polimorfismo permite tratar objetos de diferentes tipos de manera uniforme, pero ejecutar un comportamiento diferente según el tipo de objeto real que se esté utilizando.

