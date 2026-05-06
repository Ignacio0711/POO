## SOLUCION DE CONCENSIONARIO

### Clase Vehiculo
```java
public abstract class Vehiculo {
    protected int precio;
    protected String tipo;
    protected String marca;

    public Vehiculo() {
    }

    public Vehiculo(int precio, String tipo, String marca) {
        this.precio = precio;
        this.tipo = tipo;
        this.marca = marca;
    }
    
     public abstract void mostrarDetalles();
    
      public String getMarca() { return marca; }
    public String getTipo() { return tipo; }
    public double getPrecio() { return precio; }
}
```
### Clase Moto
```java
public class Moto extends Vehiculo{
    private int cilindrada;

    public Moto() {
    }

    public Moto(int cilindrada, int precio, String tipo, String marca) {
        super(precio, tipo, marca);
        this.cilindrada = cilindrada;
    }

    public int getColindrada() {
        return cilindrada;
    }

    public void setColindrada(int cilindrada) {
        this.cilindrada = cilindrada;
    }

    @Override
    public void mostrarDetalles() {
        System.out.println("Moto: " + marca + " " + tipo + 
                         " | Cilindrada: " + cilindrada + "cc" +
                         " | Precio: $" + precio);
    }
    
}
```
### Clase Auto
```java
public class Automovil extends Vehiculo{

    private int cantPuertas;
    
    public Automovil() {
    }

    public Automovil(int precio, String tipo, String marca) {
        super(precio, tipo, marca);
    }

    @Override
    public void mostrarDetalles() {
        System.out.println("Auto: " + marca + " " + tipo + 
                         " | Puertas: " + cantPuertas + 
                         " | Precio: $" + precio);
    }
}
```

### Clase Persona
```java
public class Persona {
    protected String nombre;
    protected String apellido;
    protected String dni;

    public Persona() {
    }
    
    public Persona(String nombre, String apellido, String dni) {
        this.nombre = nombre;
        this.apellido = apellido;
        this.dni = dni;
    }

    public String getNombre() {
        return nombre;
    }

    public String getApellido() {
        return apellido;
    }

    public String getDni() {
        return dni;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setApellido(String apellido) {
        this.apellido = apellido;
    }

    public void setDni(String dni) {
        this.dni = dni;
    }
  
}
```

### Clase Venta
```java
public class Venta {
   
    private Vehiculo vehiculo;
    private Persona vendedor;
    private Persona comprador;

    private static int contadorFacturas = 0;
    private int numeroFactura;

    public Venta(Vehiculo vehiculo, Persona vendedor, Persona comprador, int numeroFactura) {
        this.vehiculo = vehiculo;
        this.vendedor = vendedor;
        this.comprador = comprador;
        this.numeroFactura = ++numeroFactura;
    }
    
    public void imprimirFactura() {
        System.out.println("FACTURA N°: " + numeroFactura);
        System.out.println("----------------------");
        System.out.println("VENDEDOR: " + vendedor);
        System.out.println("COMPRADOR: " + comprador);
        System.out.println("----------------------");
        System.out.println("VEHÍCULO VENDIDO:");
        vehiculo.mostrarDetalles();  // Polimorfismo en acción
        System.out.println("----------------------");
        System.out.println("TOTAL: $" + vehiculo.getPrecio());
    }
    
    
}
```

### Clase Main
```java
public static void main(String[] args) {
        
        Persona vendedor= new Persona("Peppe", "Fig", "45110870");
        Persona comprador= new Persona("Pepito", "Gut", "45110870");
        
        Vehiculo moto= new Moto(110, 106568468, "carrera", "YAMAHA");
        Vehiculo auto= new Automovil(9926581, "RALLY", "FERRARY");
        
        Venta factura1 = new Venta(auto, vendedor, comprador, 0);
        System.out.println("--- Procesando Venta de Concesionaria ---");
        factura1.imprimirFactura();        
        System.out.println("\n------------------------------------------");
        
        Venta factura2 = new Venta(auto, vendedor, comprador, 1);
         factura2.imprimirFactura();
        
    }
```