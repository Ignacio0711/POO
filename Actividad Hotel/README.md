# POLIMORFISMO-Subtipo

### Solicion de la Actividad del Hotel

### CLASE AccionHotel
```java
public abstract class AccionHotel {
    
    public abstract void ejecutarAccion();
}
```

### CLASE Pago
```java
public abstract class AccionHotel {

   public class Pago extends AccionHotel{

    private String Tarjeta;
    private int monto;

    public Pago() {
    }

    public Pago(String Tarjeta, int monto) {
        this.Tarjeta = Tarjeta;
        this.monto = monto;
    }

    public String getTarjeta() {
        return Tarjeta;
    }

    public int getMonto() {
        return monto;
    }

    public void setTarjeta(String Tarjeta) {
        this.Tarjeta = Tarjeta;
    }

    public void setMonto(int monto) {
        this.monto = monto;
    }
    
    @Override
    public void ejecutarAccion() {
        System.out.println(this.Tarjeta + this.monto);
    }
    
} 
   
}
```
### CLASE ReservaHabitacion
```java
public class ReservaHabitacion extends AccionHotel{

    private String numHab;
    private String hues;

    public ReservaHabitacion(String numHab, String hues) {
        this.numHab = numHab;
        this.hues = hues;
    }

    public String getNumHab() {
        return numHab;
    }

    public String getHues() {
        return hues;
    }

    public void setNumHab(String numHab) {
        this.numHab = numHab;
    }

    public void setHues(String hues) {
        this.hues = hues;
    }
    
    
    
    @Override
    public void ejecutarAccion() {
        System.out.println(this.numHab + this.hues);
    }
    
}
```

### Clase Main
```java
public static void main(String[] args) {
       AccionHotel accion;
       
       accion= new ReservaHabitacion("101", "Ignacio");
       accion.ejecutarAccion();
       
       accion= new Pago("Tarjeta VISA", 35000);
       accion.ejecutarAccion();
       
    }
    
}
```