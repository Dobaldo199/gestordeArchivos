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

public class GestorArchivos
{
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
    
    public void leerArchivo(){
        Scanner leer= new Scanner(System.in);
        System.out.println("------------------------------------------");
        System.out.println("Ingrese la ruta completa del archivo");
        System.out.println("------------------------------------------");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        String texto = "";
        try{
            texto = new String(Files.readAllBytes(archivo));
            System.out.println("Este archivo contiene:\n" + texto);
        }catch(IOException e){
            System.out.println("ERROR! El archivo no pudo ser leido correctamente");
        }
    }
    
    public void leerArchivoStats(){
        Scanner leer = new Scanner(System.in);
        System.out.println("------------------------------------------");
        System.out.println("Ingrese la ruta completa del archivo");
        String ruta = leer.nextLine();
        Path archivo= Paths.get(ruta);
        String texto = "";
        try{
            texto = new String(Files.readAllBytes(archivo));
            System.out.println("\nEl contenido del archivo es:\n\n" + texto);
            System.out.println("El archivo contiene " + texto.replace(" ", "").replace("\n", "").length() + " caracteres");
            System.out.println("El archivo contiene " + texto.split("\\W+").length + " palabras");
            System.out.println("El archivo contiene " + texto.split("\\n").length + " lineas");
        }catch(IOException e){
            System.out.println("ERROR! El archivo no pudo ser leido correctamente");
        }
    }
    
    public void copiarArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("Ingrese la ruta del archivo original");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        System.out.println("Ingrese la ruta de destino de la copia");
        String newRuta = leer.nextLine();
        Path newArchivo = Paths.get(newRuta);
        try{
            Files.copy(archivo, newArchivo, StandardCopyOption.REPLACE_EXISTING);
            System.out.println("El archivo fue copiado exitosamente");
        }catch(IOException e){
            System.out.println("El archivo no pudo ser copiado");
        }
    }

    public void borrarArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("Ingrese la ruta del archivo");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        String texto = "";
        try{
            Files.deleteIfExists(archivo);
            Files.write(archivo, texto.getBytes());
            System.out.println("El contenido del archivo ha sido borrado exitosamente");
        }catch(IOException e){
            System.out.println("No se puede acceder al archivo");
        }
    }
    
    public void eliminarArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("Ingrese la ruta del archivo");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        try{
            Files.deleteIfExists(archivo);
            System.out.println("El archivo fue eliminado exitosamente");
        }catch(IOException e){
            System.out.println("El archivo no pudo ser eliminado");
        }
    }

    public void actualizarArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("Ingrese la ruta del archivo");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        System.out.println("Ingrese el texto a anexar al archivo");
        String texto = leer.nextLine();
        try{
            String orig = new String(Files.readAllBytes(archivo));
            String update = ("" + orig + texto);
            Files.deleteIfExists(archivo);
            Files.write(archivo,update.getBytes());
            System.out.println("El archivo fue actualizado exitosamente");
        }catch(IOException e){
            System.out.println("El archivo no pudo ser actualizado");
        }
    }
    
    public void vaciarArchivo(){
        Scanner leer = new Scanner(System.in);
        System.out.println("Ingrese la ruta del archivo");
        String ruta = leer.nextLine();
        Path archivo = Paths.get(ruta);
        String texto = "";
        try{
            Files.write(archivo, texto.getBytes());
            System.out.println("El archivo se ha guardado exitosamente");
        }catch(IOException e){
            System.out.println("ERROR!!");
            System.exit(1);
        }
    }
   
    
    public void agregarRegistro(){
        Scanner scan =new Scanner (System.in);
        System.out.println("Introduce dato");
        int dato=0;
        int i=0;
        do{
            dato=scant.nextInt();
            if(dato !=0){
            }
        }while(dato!=0);
        
    }
        
    public void agregarCampo(){
    }
    
    public void buscarRegistro(){
    Scanner ingreso = new Scanner (System.in);
    boolean elNumeroEsta = false;

        int num[]=new int[2];
        int x;
        for(x=0;x<num.length;x++){
            System.out.print("ingrese un numero: ");
            num[x]=ingreso.nextInt();
        }
        for(x=0;x<num.length;x++){
            System.out.println(num[x]);
        }

        System.out.print("buscar numero: ");
        int numero;
        numero=ingreso.nextInt();

        for(x=0;x<num.length;x++){
            if (numero == num[x]) {
                System.out.println("El numero esta en el indice "+x+", en la posicion "+(x+1));
                elNumeroEsta = true;
            }
        }

        if(elNumeroEsta ==false) {
            System.out.println("El numero no esta");
        }
    }
    
    public void retomarDato(){
    }
    
    public void ordenarCampo(){ \\este se ordena usando la metodologia de la burbuja
       boolean bandera = true;
       int superior = v.lenght;
       while(bandera){
          bandera = false;
          superior--;
          for(int = 0;i< superior; i++){
             if(v[i].compareTo()v[i+1])>0){
              T temp= v[i];
              v[i]=v[i+1];
              v[i+1]=temp;
              bandera = true;
             }
          }
       }
    
        
    }
    
}
