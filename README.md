import java.util.ArrayList;
import java.util.Scanner;

public class MenuAlumnos {
    static ArrayList<String> alumnos = new ArrayList<>();
    static Scanner sc = new Scanner(System.in);
    
    public static void main(String[] args) {
        int opcion;
        do {
            System.out.println("\n--- MENÚ ALUMNOS ---");
            System.out.println("1. Agregar alumno");
            System.out.println("2. Modificar alumno");
            System.out.println("3. Eliminar alumno");
            System.out.println("4. Ver lista");
            System.out.println("5. Salir");
            System.out.print("Elige una opción: ");
            opcion = sc.nextInt();
            sc.nextLine(); // limpiar buffer
            
            switch(opcion) {
                case 1: agregarAlumno(); break;
                case 2: modificarAlumno(); break;
                case 3: eliminarAlumno(); break;
                case 4: verLista(); break;
                case 5: System.out.println("¡Hasta luego!"); break;
                default: System.out.println("Opción inválida");
            }
        } while(opcion != 5);
    }
    
    public static void agregarAlumno() {
        System.out.print("Nombre del alumno: ");
        String nombre = sc.nextLine();
        alumnos.add(nombre);
        System.out.println("Alumno agregado.");
    }
    
    public static void modificarAlumno() {
        if(alumnos.isEmpty()) {
            System.out.println("No hay alumnos para modificar.");
            return;
        }
        
        System.out.println("Lista actual:");
        for(int i = 0; i < alumnos.size(); i++) {
            System.out.println(i + ": " + alumnos.get(i));
        }
        
        System.out.print("Índice del alumno a modificar: ");
        int indice = sc.nextInt();
        sc.nextLine();
        
        if(indice >= 0 && indice < alumnos.size()) {
            System.out.print("Nuevo nombre: ");
            String nuevoNombre = sc.nextLine();
            alumnos.set(indice, nuevoNombre);
            System.out.println("Alumno modificado.");
        } else {
            System.out.println("Índice inválido.");
        }
    }
    
    public static void eliminarAlumno() {
        if(alumnos.isEmpty()) {
            System.out.println("No hay alumnos para eliminar.");
            return;
        }
        
        System.out.println("Lista actual:");
        for(int i = 0; i < alumnos.size(); i++) {
            System.out.println(i + ": " + alumnos.get(i));
        }
        
        System.out.print("Índice del alumno a eliminar: ");
        int indice = sc.nextInt();
        sc.nextLine();
        
        if(indice >= 0 && indice < alumnos.size()) {
            alumnos.remove(indice);
            System.out.println("Alumno eliminado.");
        } else {
            System.out.println("Índice inválido.");
        }
    }
    
    public static void verLista() {
        if(alumnos.isEmpty()) {
            System.out.println("No hay alumnos en la lista.");
            return;
        }
        
        System.out.println("--- LISTA DE ALUMNOS ---");
        for(int i = 0; i < alumnos.size(); i++) {
            System.out.println(i + ": " + alumnos.get(i));
        }
    }
}
