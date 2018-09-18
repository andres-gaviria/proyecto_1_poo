
package proyecto;

import java.awt.Color;

import java.util.Scanner;

import javax.swing.JTextField;

public class usuario {
	//funciones
	private static Scanner teclado;
	private static int cont=1;
	private static int num,n,p,opcion;
	private static String [] telefono = new String[30];
	private static String [] cedula = new String[30];
	private static String [] nombre = new String[30];
	private static String [] salas = new String[30];
	private static String [] nombre1 = new String[30];
	private static String [] nombre_pelicula = new String[30];
	private static String [] peliculas = new String[30];
	 //_________________
	private static String [] nombre_boletos = new String[30];
	private static String [] cedula_boletos = new String[30];
	private static String [] nombre_reserva = new String[30];
	private static String [] cantidad_reserva = new String[30];
	//_________________
	public usuario() {
		nombre[0] = "";
		nombre1[0] = "";
		nombre_pelicula[0]="";
		telefono[0] = "";
		cedula[0] = "";
		salas[0]="";
		peliculas[0]=""; 
		n=1;
		//_____
		nombre_boletos[0]="";
		cedula_boletos[0]="";
		cantidad_reserva[0]="";
		nombre_reserva[0]="";
		//_____
		usuario.menu_principal();
	}
	
	public static void menu_principal(){	
	teclado = new Scanner(System.in);
	System.out.println("1. Usuario ");
	System.out.println("2. Salas ");
	System.out.println("3. Peliculas ");
	System.out.println("4. Boletos ");
	System.out.println("5. Reservas ");
	System.out.println("Opcion: ");
	opcion = teclado.nextInt();
	switch(opcion) {
	case 1:		
		usuario();
		break;
	case 2:
		salas();
		break;
	case 3:
		peliculas();
		break;
	case 4:
		boletos();
		break;
	case 5:
		reservas();
		break;
	default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");
		}
	usuario.menu_principal();
	}
	
	
	public static void reservas() {
		teclado = new Scanner(System.in);
		System.out.println("1.Crear reserva ");
		System.out.println("2.Listar reserva ");
		System.out.println("3.Editar reserva ");
		System.out.println("4.Eliminar reserva ");
		System.out.println("5.Pagar reserva ");
		System.out.println("6.Atras ");
		System.out.println("Opcion: ");
		opcion = teclado.nextInt();
		switch(opcion) {
		case 1:
			crear_reserva();
			break;
		case 2:
			listar_reserva();
			break;
		case 3:
			editar_reserva();
			break;
		case 4:
			eliminar_reserva();
			break;
		case 5:
			pagar_reserva();
			break;
		case 6:
			menu_principal();
			break;
		default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");		
		}
		usuario.menu_principal();
	}
	
	public static void crear_reserva() {
		teclado = new Scanner(System.in);
		System.out.println("Ingrese la cantidad de reservas a registrar: ");
		num = teclado.nextInt();
		System.out.println("\n");
		for(n=1;n<=num;n++){
			teclado.nextLine();
			
			System.out.println(n+" A nombre de quien se hara la reserva?: ");
			nombre_reserva[n] = teclado.nextLine();
			System.out.println(n+" Cantidad de boletas: ");
			cantidad_reserva[n] = teclado.nextLine();
			System.out.println("\n");
		}
		reservas();
	}
	public static void listar_reserva() {
		teclado.nextLine();
		for(n=cont;n<cont+num;n++){			
			System.out.println("Reserva numero:  "+(n));
			System.out.println("Nombre: "+nombre_reserva[n]);
			System.out.println("Cantidad de boletos: "+cantidad_reserva[n]);
			System.out.println("\n");
		}
		reservas();
	}
	public static void editar_reserva() {
		teclado.nextLine();
		for(n=1;n<=num;n++){
			
			System.out.println("Reserva numero:  "+(n));
			System.out.println("Nombre: "+nombre_reserva[n]);
			System.out.println("Cantidad: "+cantidad_reserva[n]);
			System.out.println("\n");
		}	
		teclado.nextLine();
		System.out.println("Suministre el id del cliente a modificar ");
		n = teclado.nextInt();
	
			teclado.nextLine();
			System.out.println("Reserva numero:  "+(n));			
			System.out.println("Suministre nombre: ");
			nombre_reserva[n] = teclado.nextLine();
			System.out.println("Suministre cantidad: ");
			cantidad_reserva[n] = teclado.nextLine();
			System.out.println("\n");
		reservas();
	}
	public static void eliminar_reserva() {
		
	}
	public static void pagar_reserva() {
		
	}
	
	
	public static void boletos() {
		teclado = new Scanner(System.in);
		System.out.println("1.Crear boleto ");
		System.out.println("2.Listar boletas ");
		System.out.println("3.Editar boleta ");
		System.out.println("4.Eliminar boleta ");
		System.out.println("5.Atras ");
		System.out.println("Opcion: ");
		opcion = teclado.nextInt();
		switch(opcion) {
		case 1:
			crear_boleto();
			break;
		case 2:
			listar_boleto();
			break;
		case 3:
			editar_boleto();
			break;
		case 4:
			eliminar_boleto();
			break;
		case 5:
			menu_principal();
				default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");		
			}
			usuario.menu_principal();
	}
	
	public static void crear_boleto() {
		teclado = new Scanner(System.in);
		System.out.println("Ingrese la cantidad de boletos a registrar: ");
		num = teclado.nextInt();
		System.out.println("\n");
		for(n=1;n<=num;n++){
			teclado.nextLine();
			
			System.out.println(n+" A nombre de quien se registrara los boletos?: ");
			nombre_boletos[n] = teclado.nextLine();
			System.out.println(n+" Suministre Cedula: ");
			cedula_boletos[n] = teclado.nextLine();
			System.out.println("\n");
		}
		usuario.boletos();
		
	}
	
	public static void listar_boleto() {
		teclado.nextLine();
		for(n=cont;n<cont+num;n++){
			
			System.out.println("Boleto numero:  "+(n));
			System.out.println("Cedula: "+cedula_boletos[n]);
			System.out.println("Nombre: "+nombre_boletos[n]);
			System.out.println("\n");
		}
		usuario.boletos();
	}
	
	public static void editar_boleto() {
		teclado.nextLine();
		for(n=1;n<cont+num;n++){
			
			System.out.println("Boleto numero:  "+(n));
			System.out.println("Cedula: "+cedula_boletos[n]);
			System.out.println("Nombre: "+nombre_boletos[n]);
		}	
		teclado.nextLine();
		System.out.println("Suministre el id del cliente a modificar ");
		n = teclado.nextInt();
	
			teclado.nextLine();
			System.out.println("Boleto numero:  "+(n));			
			System.out.println("Suministre Cedula: ");
			cedula[n] = teclado.nextLine();
			System.out.println("Suministre Nombre: ");
			nombre[n] = teclado.nextLine();
			System.out.println("\n");
		usuario.boletos();
	}
	
	public static void eliminar_boleto() {
		
	}
	
	public static void peliculas() {
		teclado = new Scanner(System.in);
		System.out.println("1.Crear peliculas ");
		System.out.println("2.Listar peliculas ");
		System.out.println("3.Editar peliculas ");
		System.out.println("4.Eliminar peliculas ");
		System.out.println("Opcion: ");
		opcion = teclado.nextInt();
		switch(opcion) {
	case 1:
		crear_peliculas();
		break;
	case 2:
		listar_peliculas();
		break;
	case 3:
		editar_peliculas();
		break;
	case 4:
		eliminar_peliculas();
		break;
		default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");		
		}
		usuario.menu_principal();
	}
	
	public static void salas() {
		teclado = new Scanner(System.in);
		System.out.println("1.Crear sala ");
		System.out.println("2.Listar salas ");
		System.out.println("3.Editar salas ");
		System.out.println("4.Eliminar salas ");
		System.out.println("Opcion: ");
		opcion = teclado.nextInt();
		switch(opcion) {
		case 1:		
			crear_salas();
			break;
		case 2:
			listar_salas();
			break;
		case 3:
			editar_salas();
			break;
		case 4:
			eliminar_salas();
			break;
		default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");
		}
		usuario.menu_principal();
	}
	
	public static void usuario() {
		teclado = new Scanner(System.in);
		System.out.println("1.Crear usuario ");
		System.out.println("2.Listar usuario ");
		System.out.println("3.Editar usuario ");
		System.out.println("4.Eliminar usuario ");
		System.out.println("Opcion: ");
		opcion = teclado.nextInt();
		switch(opcion) {
		case 1:		
			crear_usuario();
			break;
		case 2:
			listar_usuarios();
			break;
		case 3:
			editar_usuario();
			break;
		case 4:
			eliminar_usuario();
			break;
		default: System.out.println("Suministre una opcion correcta, vuelve a intentarlo");
		}
		usuario.menu_principal();
	}
	
	public static void crear_usuario() {
		teclado = new Scanner(System.in);
		System.out.println("SUMINISTRE LA CANTIDAD DE CLIENTES A REGISTRAR: ");
		num = teclado.nextInt();
		System.out.println("\n");
		for(n=1;n<=num;n++){
			teclado.nextLine();
			System.out.println(n+" Suministre Cedula: ");
			cedula[n] = teclado.nextLine();
			System.out.println(n+" Suministre Nombre: ");
			nombre[n] = teclado.nextLine();
			System.out.println(n+"Suministre Telefono: ");
			telefono[n] = teclado.nextLine();
			System.out.println("\n");
		}
		
	}
	public static void listar_usuarios() {
		for(n=cont;n<cont+num;n++){
			teclado.nextLine();
			System.out.println("cliente numero:  "+(n));
			System.out.println("Cedula: "+cedula[n]);
			System.out.println("Nombre: "+nombre[n]);
			System.out.println("Telefono: "+telefono[n]);
			System.out.println("\n");
		}
	}
	
	

	public static void editar_usuario() {
		for(n=1;n<=num;n++){
			teclado.nextLine();
			System.out.println("cliente numero:  "+(n));
			System.out.println("Cedula: "+cedula[n]);
			System.out.println("Nombre: "+nombre[n]);
			System.out.println("Telefono: "+telefono[n]);
		
		}	
		teclado.nextLine();
		System.out.println("Suministre el id del cliente a modificar ");
		n = teclado.nextInt();
	
			teclado.nextLine();
			System.out.println("Usuario numero:  "+(n));
			
			System.out.println("Suministre Cedula: ");
			cedula[n] = teclado.nextLine();
			System.out.println("Suministre Nombre: ");
			nombre[n] = teclado.nextLine();
			System.out.println("Suministre Telefono: ");
			telefono[n] = teclado.nextLine();
			System.out.println("\n");
		menu_principal();
	}
	public static void eliminar_usuario() {
			
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		usuario usuario=new usuario();

	}
	public static void crear_salas() {
		teclado = new Scanner(System.in);
		System.out.println("SUMINISTRE LA CANTIDAD DE SALAS A REGISTRAR: ");
		num = teclado.nextInt();
		System.out.println("\n");
		for(n=1;n<=num;n++){
			teclado.nextLine();
			System.out.println(n+" Suministre sala: ");
			salas[n] = teclado.nextLine();
			System.out.println(n+" Suministre Nombre de sala: ");
			nombre1[n] = teclado.nextLine();
			System.out.println("\n");
		}
		
	}
	public static void listar_salas() {
		for(n=cont;n<cont+num;n++){
			teclado.nextLine();
			System.out.println("numero de sala:  "+(n));
			System.out.println("Nombre1: "+nombre1[n]);
			System.out.println("\n");
		}
	}
	public static void editar_salas() {
		for(n=1;n<=num;n++){
			teclado.nextLine();
			System.out.println("cliente numero:  "+(n));
        	System.out.println("Nombre1: "+nombre1[n]);
			
		
		}	
		teclado.nextLine();
		System.out.println("Suministre el id del cliente a modificar ");
		n = teclado.nextInt();
	
			teclado.nextLine();
			System.out.println("sala numero:  "+(n));
			
			System.out.println("Suministre salas: ");
			salas[n] = teclado.nextLine();
			System.out.println("Suministre Nombre de salas: ");
			nombre1[n] = teclado.nextLine();
			
			System.out.println("\n");
		menu_principal();
	}
public static void eliminar_salas() {
		
		
	}
public static void crear_peliculas() {
	teclado = new Scanner(System.in);
	System.out.println("SUMINISTRE LA CANTIDAD DE PELICULAS A REGISTRAR: ");
	num = teclado.nextInt();
	System.out.println("\n");
	for(n=1;n<=num;n++){
		teclado.nextLine();
		System.out.println(n+" Suministre peliculas: ");
		peliculas[n] = teclado.nextLine();
		System.out.println(n+" Suministre Nombre de pelicula: ");
		nombre_pelicula[n] = teclado.nextLine();
		System.out.println("\n");
	}
	
 }
public static void listar_peliculas() {
	for(n=cont;n<cont+num;n++){
		teclado.nextLine();
		System.out.println("numero de peliculas:  "+(n));
		System.out.println("Nombre: "+peliculas[n]);
		System.out.println("nombre de pelicula:  "+(n));
		System.out.println("Nombre: "+nombre_pelicula[n]);
		System.out.println("\n");
	}
 }

public static void editar_peliculas() {
	for(n=1;n<=num;n++){
		teclado.nextLine();
		System.out.println("cliente numero:  "+(n));
    	System.out.println("Nombre1: "+nombre1[n]);
		
	
	}	
	teclado.nextLine();
	System.out.println("Suministre el id de la pelicula a modificar ");
	n = teclado.nextInt();
		teclado.nextLine();
		System.out.println(" pelicula numero:  "+(n));
		
		System.out.println("Suministre peliculas: ");
		peliculas[n] = teclado.nextLine();
		System.out.println("Suministre Nombre de pelicula: ");
		nombre_pelicula[n] = teclado.nextLine();
		
		System.out.println("\n");
	menu_principal();
}
public static void eliminar_peliculas() {
	
	
}
}
