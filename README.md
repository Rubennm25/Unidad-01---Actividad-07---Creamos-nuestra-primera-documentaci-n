# Proyecto: Videojuego RPG de Acción y Fantasía ( en UNREAL ENGINE 5 )

## 1. Fundamentos del sistema
**Objetivos del sistema:**
El objetivo es desarrollar un software de aplicación (Videojuego) distribuido de forma privada mediante un único pago y código cerrado. El juego será un RPG de acción en un entorno 3D desarrollado con el motor **Unreal Engine 5**. El jugador controlará un avatar capaz de realizar desplazamientos, saltos, ataques y defensa con diferentes armas. El sistema incluirá gestión de inventario, interacción con el entorno y un modo multijugador cooperativo para hasta 5 usuarios.

## 2. Análisis y especificación de requisitos
Información extraída de la documentación del proyecto.

### Requisitos Funcionales
* **Sistema de Combate:** El software permitirá controlar un avatar en 3D, ejecutando acciones complejas y calculando colisiones y daño en tiempo real.
* **Gestión de Inventario:** Base de datos interna para ítems, permitiendo equipar y soltar objetos, limitado por una estadística de peso/carga máxima.
* **Multijugador Cooperativo:** Módulo de red que permite la conexión de hasta 5 usuarios simultáneos, sincronizando posición y animaciones.
* **Persistencia:** Sistema de serialización para autoguardado local y en la nube.
* **Inteligencia Artificial:** Control de PNJs y enemigos, cuya dificultad es predeterminada y no escala con el nivel del jugador.

### Requisitos No Funcionales
* **Rendimiento:** Tasa de refresco estable de 60 FPS en hardware alto y mínimo de 30 FPS en medio.
* **Latencia de Red:** Optimización de paquetes para mantener una latencia inferior a 100 ms en multijugador.
* **Compatibilidad:** Compatible con Windows 10/11 y soporte para teclado/ratón y mandos (Xbox/PlayStation).
* **Escalabilidad:** Código estructurado para permitir futuros DLCs sin reescritura.

## 3. Diseño
Para la gestión del ciclo de vida se ha determinado el uso de la **Metodología Ágil (Scrum)**.

Técnicas descriptivas utilizadas:
* **Brainstorming:** Usado por el equipo de diseño para definir narrativa y estilo.
* **Prototipado:** Creación de versiones rápidas de mecánicas de combate y salto.
* **Análisis de la Competencia:** Investigación de otros RPGs exitosos para fijar estándares de calidad.

### Diagrama del Sistema
![Diagrama de Arquitectura](ruta/a/tu/imagen.png)

## 4. Implementación
A continuación se muestra la refactorización del código "feo" de la Actividad 05, aplicando normas de estilo Java y Javadoc.

```java
/**
 * Representa a un estudiante con nombre, edad y calificación.
 */
class Alumno {
    /** Nombre del alumno. */
    private String nombre;
    /** Edad del alumno. */
    private int edad;
    /** Nota final del curso. */
    private double notaFinal;

    /**
     * Constructor para crear un alumno.
     * @param nombre Nombre del alumno.
     * @param edad Edad del alumno.
     * @param notaFinal Calificación obtenida.
     */
    public Alumno(String nombre, int edad, double notaFinal) {
        this.nombre = nombre;
        this.edad = edad;
        this.notaFinal = notaFinal;
    }

    /**
     * Imprime los datos del alumno en consola.
     */
    public void mostrarDatos() {
        System.out.println("Alumno: " + nombre + ", Edad: " + edad + ", Nota Final: " + notaFinal);
    }

    /**
     * Muestra un mensaje personalizado según si aprobó o no.
     */
    public void mostrarMensajeFinal() {
        if (notaFinal >= 5.0) {
            System.out.println("¡Felicidades " + nombre + ", aprobaste!");
        } else {
            System.out.println("Lo siento " + nombre + ", no aprobaste.");
        }
    }
}

/**
 * Representa un curso que contiene una lista de alumnos.
 */
class Curso {
    /** Nombre del curso. */
    private String nombreCurso;
    /** Lista de alumnos inscritos. */
    private Alumno[] listaAlumnos;

    /**
     * Constructor del curso.
     * @param nombreCurso Nombre de la asignatura.
     * @param listaAlumnos Array de objetos Alumno.
     */
    public Curso(String nombreCurso, Alumno[] listaAlumnos) {
        this.nombreCurso = nombreCurso;
        this.listaAlumnos = listaAlumnos;
    }

    /**
     * Muestra el nombre del curso y procesa la información de todos los alumnos.
     */
    public void mostrarTodo() {
        System.out.println("Curso: " + nombreCurso);
        System.out.println("-------------------------");
        for (Alumno alumno : listaAlumnos) {
            alumno.mostrarDatos();
            alumno.mostrarMensajeFinal();
            System.out.println(); 
        }
    }
}
