# Semana-7
Hola

public abstract class Figura {
    private String nombre_fig;
    private String tipo_fig;
    
    //no tiene cuerpo el metodo abstracto
    public abstract void dibujar();
    
    
    
    public void escalar(){}
    
    public void pintar(){}
    
    public abstract void mover();

    public String getNombre_fig() {
        return nombre_fig;
    }
    public void setNombre_fig(String nombre_fig) {
        this.nombre_fig = nombre_fig;
    }

    public String getTipo_fig() {
        return tipo_fig;
    }
    public void setTipo_fig(String tipo_fig) {
        this.tipo_fig = tipo_fig;
    }        
    
}




public abstract class FPlana extends Figura {
    private int nlados_fp;
    private double angCentral_fp;
    
    //ideal hacer estos metodos abstractos para que los hijos sobreescriban
    public double calcu_area(){
        return 0;
    }
    
    public double calcu_perimetro(){
        return 0;
    }
    
    public abstract String reporte();

    public int getNlados_fp() {
        return nlados_fp;
    }
    public void setNlados_fp(int nlados_fp) {
        this.nlados_fp = nlados_fp;
    }

    public double getAngCentral_fp() {
        return angCentral_fp;
    }
    public void setAngCentral_fp(double angCentral_fp) {
        this.angCentral_fp = angCentral_fp;
    }
  
    @Override
    public void dibujar() {
        System.out.println("La figura plana se dibuja");
    }

    @Override
    public void mover() {
        System.out.println("La figura plana se esta moviendo");
    }
   
}


public class Cuadrado extends FPlana {

    private float lado;

    public Cuadrado() {
    }
 
    

    public float getLado() {
        return lado;
    }
    public void setLado(float lado) {
        this.lado = lado;
    }
    
    //sobreescritura opcional de metodos

    @Override
    public double calcu_area() {
        return lado*lado;
    }

    @Override
    public double calcu_perimetro() {
        return 4*lado;
    }

    @Override
    public int getNlados_fp() {
        return 4;
    }

    @Override
    public double getAngCentral_fp() {
        return 90;    
    }

    @Override
    public String getNombre_fig() {
        return "Cuadrado";
    }

    @Override
    public String getTipo_fig() {
        return "Figura Plana";
    }
    
    
    
    @Override
    public String reporte() {
        String salida="\n Reporte de cuadrado: "+
                "\n Valor de lado: "+ getLado() +
                "\n Numero de lado: "+ getNlados_fp() +
                "\n Angulo de lado: "+ getAngCentral_fp() +
                "\n Nombre de figura: "+ getNombre_fig() +
                "\n Tipo de figura: "+ getTipo_fig();
        
         return salida;
    }
    
}


public class Circunferencia extends FPlana {
    
     private float radio;

    public Circunferencia() {
    }

    public float getRadio() {
        return radio;
    }
    public void setRadio(float radio) {
        this.radio = radio;
    }
    
    @Override
    public double calcu_area() {
        return 3.14156*radio*radio;
    }

    @Override
    public double calcu_perimetro() {
        return 2*3.14156*radio;
    }

    @Override
    public int getNlados_fp() {
        return 0;
    }

    @Override
    public double getAngCentral_fp() {
        return 360;    
    }

    @Override
    public String getNombre_fig() {
        return "Circunferencia";
    }

    @Override
    public String getTipo_fig() {
        return "Figura Plana";
    }
    

    @Override
    public String reporte() {
        String exit="\n Reporte de la circunferencia: "+
                "\n Radio de la circunferencia: "+ getRadio() +
                "\n Numero de lados de la circunferencia: "+ getNlados_fp() +
                "\n Angulo de la circunferencia: "+ getAngCentral_fp() +
                "\n Nombre de figura: "+ getNombre_fig() +
                "\n Tipo de figura: "+ getTipo_fig();
        
         return exit;
    }
    
}


public class _Principal {
    
    public static void main(String[] args) {
        System.out.println("1 era instancia del tipo figura");
        
        // cannot be posible Figura f01 = new Figura ();
        
        Cuadrado c01 = new Cuadrado();
        c01.setLado(2);
        
        System.out.println("Nombre de la figura: " + c01.getNombre_fig());
        System.out.println("Perimetro de cuadrado: " + c01.calcu_perimetro());
        System.out.println("Area de cuadrado: " + c01.calcu_area());
        
        System.out.println("\n\n *****************************************");
        System.out.println(c01. reporte());
        
        
        c01.setAngCentral_fp(90);
        c01.setNlados_fp(4);
        c01.setNombre_fig("Cuadrado");
        c01.setTipo_fig("Figura Plana");
        
        
        System.out.println("\n\n2 da instancia del tipo figura");
        
         Circunferencia cir01 = new Circunferencia();
        cir01.setRadio(5);
        System.out.println("Nombre de la figura: " + cir01.getNombre_fig());
        System.out.println("Perimetro del circulo: " + cir01.calcu_perimetro());
        System.out.println("Area del circulo: " + cir01.calcu_area());
        
        System.out.println("\n\n *****************************************");
        System.out.println(cir01. reporte());
        
        
        cir01.setAngCentral_fp(360);
        cir01.setNlados_fp(0);
        cir01.setNombre_fig("Circulo");
        cir01.setTipo_fig("Figura Plana");
    }
}
