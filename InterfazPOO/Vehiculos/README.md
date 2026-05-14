## <center> POO-INTERFAZ
## Acciones de Vehiculos

### Interfaz 1: IVehiculo
```java
public interface IVehiculo {
    public void moover ();
}
``` 

### Interfaz 2: IVolador
```java
public interface IVolador {
    public void volar();
}
``` 

### Clase Avion
```java
public class Avion implements IVolador{

    @Override
    public void volar() {
        System.out.println("El avion esta volando");
    }
}
``` 

### Clase Automovil
```java
public class Automovil implements IVehiculo{
    private String patente= "AA22BB";

    @Override
    public void moover() {
        System.out.println("Patente del auto:"+patente);
    }  
}
``` 

### Clase Hidroavion
```java
public class Hidroavion implements IVehiculo, IVolador{

    @Override
    public void moover() {
        System.out.println("El hidroavion se esta moviendo");
    }

    @Override
    public void volar() {
        System.out.println("El hidroavion esta volando");
    }
}
``` 

### Clase Main
```java
public static void main(String[] args) {
        Hidroavion hidroavion1;
        Automovil auto;
        Avion miAvion;
        
        hidroavion1 = new Hidroavion();
        hidroavion1.moover();
        hidroavion1.volar();
        
        auto= new Automovil();
        auto.moover();
        
        miAvion= new Avion();
        miAvion.volar(); 
    } 
```