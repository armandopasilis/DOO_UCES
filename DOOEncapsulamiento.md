# Encapsulamiento   
____________________________________________________________________________________________
_Explicación de Encapsulamiento como principio y su importancia en el diseño orientado a objetos._ 

El encapsulamiento es el segundo pilar de OOP y se refiere al proceso de agrupar datos (atributos) y métodos (funciones) que operan sobre esos datos dentro de una única unidad o clase, y restringir el acceso directo a los datos. El propósito del encapsulamiento es proteger el estado interno de un objeto y garantizar que solo pueda ser modificado a través de métodos específicos (los llamados métodos de acceso o getters/setters).

En tu código:
La clase Usuario tiene un atributo nombre, que es protegido (con el modificador protected). Esto significa que las subclases pueden acceder a este atributo, pero el acceso desde fuera de la clase está restringido.

La clase Bibliotecario, como subclase de Usuario, puede acceder y modificar directamente el nombre, pero el acceso al atributo está controlado, lo que ayuda a proteger el estado del objeto.
____________________________________________________________________________________________
Ejemplo en el proyecto 
Incluir un diagrama UML que muestra cómo la clase o las clases del proyecto se relacionan entre sí al aplicar Encapsulamiento. Incluir una imagen incrustada, así como el enlace correctamente referenciado para ver el diagrama en detalle. Describe cómo el diagrama de las clases seleccionadas refleja el Encapsulamiento.
____________________________________________________________________________________________
## Imagen
![image](https://github.com/user-attachments/assets/566fa402-1afd-4cc3-81d0-670f9bf9c334)
____________________________________________________________________________________________
## Ejemplo de Código 
Incluir un fragmento de código que demuestre la implementación de Encapsulamiento en el proyecto (puede ser pseudocódigo o un lenguaje como JavaScript, Python o Java).
´´´JAVA
// Clase Usuario con encapsulamiento
public class Usuario {
    // Atributo privado para proteger el estado del objeto
    private String nombre;

    // Constructor que inicializa el nombre
    public Usuario(String nombre) {
        this.nombre = nombre;
    }

    // Getter para obtener el nombre (acceso controlado)
    public String getNombre() {
        return nombre;
    }

    // Setter para modificar el nombre (acceso controlado)
    public void setNombre(String nombre) {
        // Validación antes de modificar el nombre (ejemplo de control)
        if (nombre != null && !nombre.isEmpty()) {
            this.nombre = nombre;
        } else {
            System.out.println("El nombre no puede estar vacío.");
        }
    }
}

// Subclase Bibliotecario que hereda de Usuario
public class Bibliotecario extends Usuario {
    private int idBibliotecario;

    // Constructor que inicializa el nombre y el idBibliotecario
    public Bibliotecario(String nombre, int idBibliotecario) {
        super(nombre);  // Llama al constructor de la clase Usuario
        this.idBibliotecario = idBibliotecario;
    }

    // Método para obtener información del bibliotecario
    public String obtenerInformacion() {
        return "Bibliotecario: " + getNombre() + " - ID: " + idBibliotecario;
    }
}

// Clase principal para probar el código
public class Main {
    public static void main(String[] args) {
        // Creación de un objeto Bibliotecario
        Bibliotecario bibliotecario = new Bibliotecario("Carlos", 101);

        // Usando el método getter para acceder al nombre de manera controlada
        System.out.println("Nombre inicial: " + bibliotecario.getNombre());  // Carlos

        // Usando el método setter para modificar el nombre de manera controlada
        bibliotecario.setNombre("Juan");
        System.out.println("Nombre modificado: " + bibliotecario.getNombre());  // Juan

        // Intentando establecer un nombre inválido (vacío)
        bibliotecario.setNombre("");
        System.out.println("Nombre tras intento inválido: " + bibliotecario.getNombre());  // Juan

        // Llamada al método obtenerInformacion() para obtener datos del bibliotecario
        System.out.println(bibliotecario.obtenerInformacion());  // Bibliotecario: Juan - ID: 101
    }
}
´´´
