# gestordeArchivos
lugar pa trabajar en progra con los de pana
(PA REVISARLO COPIEN Y REVISEN EN NETBEANS JEJE)

------------------------------------------------------------------------------------------------------------------------------

import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.Files;
import java.nio.file.StandardCopyOption;
import java.io.IOException;
import java.util.Scanner;

public class Gestor
{
    int i = 0;
    int j = 0;
    int contadorI=0;
    Scanner teclado = new Scanner(System.in);
    String [][] array;
    
     public void crearDirectorio(){
        Scanner leer = new Scanner(System.in);
        System.out.println("------------------------------------------");
        System.out.println("Ingrese la ruta commpleta del directorio.");
        System.out.println("------------------------------------------");
        String ruta= leer.nextLine();
        Path directorio = Paths.get(ruta);
        if(Files.exists(directorio)){
            System.out.println("El directorio ya existe");
        }else{
            try{
                Files.createDirectories(directorio);
                System.out.println("El directorio fue creado exitosamente");
            }catch(IOException e){
                System.out.println("El directorio no pudo ser creado");
            }
        }
    }
    
     public void crearArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("------------------------------------------");
        System.out.println("Ingrese la ruta completa del archivo");
        System.out.println("------------------------------------------");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        System.out.println("------------------------------------------");
        System.out.println("Ingrese el texto a guardar en el archivo");
        System.out.println("------------------------------------------");
        String texto = leer.nextLine();
        try{
            Files.write(archivo, texto.getBytes());
            System.out.println("El archivo se ha guardado exitosamente");
        }catch(IOException e){
            System.out.println("Error! El archivo no pudo ser guardado");
        }
    }
    
    public void crearArreglo(){
        System.out.println("-------------------------------------------");
        System.out.println("Ingrese largo del arreglo");
        i = teclado.nextInt();
        System.out.println("-------------------------------------------");
        System.out.println("Ingrese ancho del arreglo");
        j = teclado.nextInt();
        this.array = new String [i][j];
    }
    
    public void ingresarDescripcion(){
        System.out.println("-------------------------------------------");
        System.out.println("Ingrese nombre de *nombre/dato*");
        this.array [1][0] = teclado.nextLine();
        
    }
    
    public void ingresarDatos(){
        System.out.println("-------------------------------------------");
        System.out.println("Seleccione fila y a rellenar");
        int fila =teclado.nextInt();
        if(contadorI !=i){
            do{
                for(contadorI=2; contadorI<i; contadorI++){
                    System.out.println("----------------------------------");
                    System.out.println("Ingresa los datos *NOTAS O NUMEROS*");
                    this.array [i][fila] = teclado.nextLine();
                }
            }while(contadorI!= i);
        }
        
    }
    
    public void grabarArreglo(){
        for(int contadorI=0; contadorI<i; contadorI++){
            System.out.println("---------------------------------------");
            System.out.println("");
        }
    }
    
    public void buscarDato(){
    }
    
    public void ordenarDatos(){
        System.out.println("-------------------------------------------");
        System.out.println("Ingrese el campo a evaluar");
        int campo = teclado.nextInt();
        
    }
    
}
