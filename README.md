public interface DescuentoCalculable {
    double calcularDescuento();
}

public abstract class Tienda implements DescuentoCalculable {
    protected String nombreTienda;
    protected String tipoDeComercio;
    protected double descuento;

    public Tienda(String nombreTienda, String tipoDeComercio, double descuento) {
        this.nombreTienda = nombreTienda;
        this.tipoDeComercio = tipoDeComercio;
        this.descuento = descuento;
    }

    public abstract void imprimirDetallesTienda();
}

public class RopaNino extends Tienda {
    public RopaNino(String nombreTienda, String tipoDeComercio, double descuento) {
        super(nombreTienda, tipoDeComercio, descuento);
    }

    @Override
    public double calcularDescuento() {
        return descuento * 0.08;
    }

    @Override
    public void imprimirDetallesTienda() {
        System.out.println("Nombre de la tienda: " + nombreTienda);
        System.out.println("Tipo de comercio: " + tipoDeComercio);
        System.out.println("Descuento: " + descuento);
    }
}

public class DispositivosElectronicos extends Tienda {
    public DispositivosElectronicos(String nombreTienda, String tipoDeComercio, double descuento) {
        super(nombreTienda, tipoDeComercio, descuento);
    }

    @Override
    public double calcularDescuento() {
        return descuento * 0.04;
    }

    @Override
    public void imprimirDetallesTienda() {
        System.out.println("Nombre de la tienda: " + nombreTienda);
        System.out.println("Tipo de comercio: " + tipoDeComercio);
        System.out.println("Descuento: " + descuento);
    }
}

// Agregar más clases para tipos adicionales de comercio si es necesario

public class CentroComercialTester {
    public static void main(String[] args) {
        Tienda ropaNino = new RopaNino("KidsFashion", "Ropa de niño", 500.0);
        Tienda dispositivosElectronicos = new DispositivosElectronicos("TechZone", "Dispositivos Electrónicos", 1000.0);

        // Agregar más tiendas aquí

        imprimirDetallesTienda(ropaNino);
        imprimirDetallesTienda(dispositivosElectronicos);
    }

    public static void imprimirDetallesTienda(Tienda tienda) {
        tienda.imprimirDetallesTienda();
        System.out.println("Descuento calculado: " + tienda.calcularDescuento());
    }
}
