# <center> POO- INTERFAZ
## Calcular area y perimetro de figuras

### Interfaz- ICalcular
```java
public interface ICalcular {
    public double calculoArea();
    public double calculoPerimetro();  
}
```

### Clase Triangulo
```java
public class Triangulo implements ICalcular{

    private double base=3;
    private double altura=4;
    private double hipotenusa=5;
    private double area;
    private double parametro;
    
    @Override
    public double calculoArea() {
        area= (base* altura)/2;
        return area;   
    }
    @Override
    public double calculoPerimetro() {
       parametro=base+altura+hipotenusa;
        return parametro;
       
    }
}
```

### Clase Circulo
```java
public class Circulo implements ICalcular{
    private double PI= 3.14;
    private double radio=5;
    private double area;
    private double perimentro;
    
    @Override
    public double calculoArea() {
        area=PI*(radio*radio); 
        return area;
    }

    @Override
    public double calculoPerimetro() {
        perimentro=2*PI*radio;
        return perimentro;   
    }
}
```

### Clase main
```java
public static void main(String[] args) {
        Circulo miCirculo= new Circulo();
        Triangulo miTriangulo= new Triangulo();
        
        ICalcular miCirculo1= miCirculo;
        ICalcular miTriangulo1=miTriangulo;
        
        System.out.println("El area del cirulo es :"+miCirculo1.calculoArea());
        System.out.println("El area del triangulo es :"+miTriangulo1.calculoArea());
        System.out.println("El perimetro del cirulo es :"+miTriangulo1.calculoPerimetro());
        System.out.println("El perimetro del cirulo es :"+miCirculo1.calculoPerimetro());
        
    }
}
```