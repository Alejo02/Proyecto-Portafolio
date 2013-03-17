Proyecto-Portafolio
===================
import javax.swing.*;

import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

/**
 * Uniminuto 2013
 * AppPortafolioBancario 
 * Clase que tiene toda la interfaz grafica del programa. 
 * @file name: AppPortafolioBancario.java
 * @version: 1.0
 * @author Jeyson Alejandro Velasco
 * Tec.Informatica-3 semestre
 */

public class AppPortafolioBancario extends JFrame implements ActionListener{
  
	private JPanel pnlTitulo;
	private JPanel pnlTransacciones;
	private JPanel pnlBotones;
	private JLabel lblTitulo;   // JLabel lbl documentocliente, JTextField documentocliente
	private JLabel lblDocumentoCliente;
	private JTextField txtDocumentoCliente;
	private Container contenedor;
	private JLabel lblValor;
	private JTextField txtValor;
	private JLabel lblSaldo;
	private JTextField txtSaldo;
	private JLabel lblNombre;
	private JTextField txtNombre;
	private JLabel lblApellido;
	private JTextField txtApellido;
	private JLabel lblTelefono;
	private JTextField txtTelefono;
	
	private JButton btnConsignarCuentaAhorros;
	private JButton btnConsignarCuentaCorriente;
	private JButton btnRetirarCuentaAhorros;
	private JButton btnRetirarCuentaCorriente;
	private JButton btnConsultarSaldoCuentaAhorros;
	private JButton btnConsultarSaldoCuentaCorriente;
	private JButton btnLimpiar;
	private JButton btnSalir;
	private Cliente unCliente;
	private JButton btnRegistrarClienteCuentaAhorros;
	private JButton btnRegistrarClienteCuentaCorriente;
	private CuentaAhorros unaCuentaAhorros;
	private CuentaCorriente unaCuentaCorriente;
	
	/**
	 * 
	 */
	
	public AppPortafolioBancario() {
		
		/**
		 * Definicion objetos del panel del titulo
		 */
	
		
		this.pnlTitulo = new JPanel();
		this.lblTitulo = new JLabel("Portafolio Bancario");
		pnlTitulo.add(lblTitulo);
		
		/**
		 * Definicion objetos del panel de transaccion
		 */
		
		
		this.pnlTransacciones = new JPanel();
		pnlTransacciones.setLayout(new GridLayout(3,1));
		this.lblValor = new JLabel("Valor");
		this.txtValor = new JTextField(10);
		this.lblSaldo = new JLabel("Saldo");
		this.txtSaldo = new JTextField(10);
		this.lblDocumentoCliente = new JLabel("Documento Cliente");
		this.txtDocumentoCliente = new JTextField(10);
		this.lblNombre=new JLabel ("Nombre Cliente");
		this.txtNombre=new JTextField(10);
		this.lblApellido=new JLabel("Apellido cliente");
		this.txtApellido= new JTextField(10);
		this.lblTelefono= new JLabel("Telefono Cliente");
		this.txtTelefono=new JTextField(10);
		
		
		pnlTransacciones.add(lblDocumentoCliente);
		pnlTransacciones.add(txtDocumentoCliente);
		pnlTransacciones.add(lblNombre);
		pnlTransacciones.add(txtNombre);
		pnlTransacciones.add(lblApellido);
		pnlTransacciones.add(txtApellido);
		pnlTransacciones.add(lblTelefono);
		pnlTransacciones.add(txtTelefono);
		pnlTransacciones.add(lblValor);
		pnlTransacciones.add(txtValor);
		pnlTransacciones.add(lblSaldo);
		pnlTransacciones.add(txtSaldo);
		this.contenedor = getContentPane();
		contenedor.setLayout(new BorderLayout()); 
		contenedor.add(pnlTitulo, BorderLayout.NORTH);	
		contenedor.add(pnlTransacciones, BorderLayout.CENTER);
		
		/**
		 * Se instancian objetos panel de los botones
		 */
		 
		
		this.pnlBotones = new JPanel();
		this.pnlBotones.setLayout(new GridLayout(5,2)); // cuatro filas 2 columnas
		this.btnConsignarCuentaAhorros = new JButton("Consignar cuenta ahorros");
		this.btnConsignarCuentaCorriente = new JButton("Consignar cuenta corriente");
		this.btnRetirarCuentaAhorros = new JButton("Retirar cuenta ahorros");
		this.btnRetirarCuentaCorriente = new JButton("Retirar cuenta corriente");
		this.btnConsultarSaldoCuentaAhorros = new JButton("Consultar saldo cuenta ahorros");
		this.btnConsultarSaldoCuentaCorriente = new JButton("Consultar saldo cuenta corriente");
		this.btnRegistrarClienteCuentaAhorros=new JButton("Registrar Cuenta Ahorros");
		this.btnRegistrarClienteCuentaCorriente = new JButton("Registrar Cuenta Corriente");
		this.btnLimpiar = new JButton("Limpiar");
		this.btnSalir = new JButton("Salir");
		
		
		btnConsignarCuentaAhorros.addActionListener(this);
		btnConsignarCuentaCorriente.addActionListener(this);
		btnRetirarCuentaAhorros.addActionListener(this);
		btnRetirarCuentaCorriente.addActionListener(this);
		btnConsultarSaldoCuentaAhorros.addActionListener(this);
		btnConsultarSaldoCuentaCorriente.addActionListener(this);
		btnRegistrarClienteCuentaAhorros.addActionListener(this);
		btnRegistrarClienteCuentaCorriente.addActionListener(this);
		btnLimpiar.addActionListener(this);
		btnSalir.addActionListener(this);
		
		
		
		pnlBotones.add(btnConsignarCuentaAhorros);
		pnlBotones.add(btnConsignarCuentaCorriente);
		pnlBotones.add(btnRetirarCuentaAhorros);
		pnlBotones.add(btnRetirarCuentaCorriente);
		pnlBotones.add(btnConsultarSaldoCuentaAhorros);
		pnlBotones.add(btnConsultarSaldoCuentaCorriente);
		pnlBotones.add(btnRegistrarClienteCuentaAhorros);
		pnlBotones.add(btnRegistrarClienteCuentaCorriente);
		pnlBotones.add(btnLimpiar);
		pnlBotones.add(btnSalir);
		
		contenedor = getContentPane();
		contenedor.add(pnlBotones, BorderLayout.SOUTH);
		
			
		/**
		 * Las siguientes lineas de codigo sirve para crear la ventana 
		 * donde se llevara acabo toda la interfaz grafica 
		 * aqui se le da el tamaño a la ventana, la muestra si es visible 
		 * si se puede agrandar y centrar la ventana en la pantalla 
		 */
		
		setSize(530,240); //Tamaño de la ventana
		setVisible(true);
		setLocationRelativeTo(null); // Centra la ventada en la pantalla
		setResizable(true); // Permite que el usuario agrande la ventana
		
	
		
	}
	
	/**
	 * Metodo que registra al cliente en la cuenta ahorros
	 */
	
	private void registrarClienteAhorros (){
		long  documento =Long.parseLong(txtDocumentoCliente.getText()) ;
		String nombre = txtNombre.getText();
		String apellido=txtApellido.getText();
		String telefono= txtTelefono.getText();
		double valor = Double.parseDouble(txtValor.getText());
		this.unCliente =new Cliente(documento,nombre,apellido,telefono);
		this.unaCuentaAhorros = new CuentaAhorros (unCliente,documento,valor);
	}
	
	/**
	 * Metodo que registra al cliente en la cuenta corriente
	 */
	
	private void registrarClienteCorriente (){
		
		long  documento =Long.parseLong(txtDocumentoCliente.getText()) ;
		String nombre = txtNombre.getText();
		String apellido=txtApellido.getText();
		String telefono= txtTelefono.getText();
		double valor = Double.parseDouble(txtValor.getText());
		this.unCliente =new Cliente(documento,nombre,apellido,telefono);
		this.unaCuentaCorriente = new CuentaCorriente (unCliente,documento,valor);
		
	}
	
	/**
	 * Metodo que consigna a la cuenta ahorrros 
	 * la cantiodad ingresa por el usuario 
	 */
	
	private void consignarAhorros (){
		double cantidad= Double.parseDouble(txtValor.getText());
		unaCuentaAhorros.consignar(cantidad);
	}
	
	/**
	 * Metodo que consigna a la cuenta corriente 
	 * la cantiodad ingresa por el usuario 
	 */
	private void consignarCorriente (){
		double cantidad= Double.parseDouble(txtValor.getText());
		unaCuentaCorriente.consignar(cantidad);
		
	}
	/**
	 * Metodo que retira de la cuenta ahorros una cantidad 
	 * determinada que ingresa el usuario
	 */
	
	private void retirarAhorros (){
		
		double cantidad= Double.parseDouble(txtValor.getText());
		unaCuentaAhorros.retirar(cantidad);
		
	}
	/**
	 * Metodo que retira de la cuenta corriente una cantidad 
	 * determinada que ingresa el usuario
	 */
	
	private void retirarCorriente (){
	 
		double cantidad= Double.parseDouble(txtValor.getText());
		unaCuentaCorriente.retirar(cantidad);
		
	}
	
	public static void main(String[] args) {
		new AppPortafolioBancario();
	}

	/**
	 * Metodo que efectua todas las acciones 
	 * que el cliente desee mediante los botones creados
	 */
	
	@Override
	public void actionPerformed(ActionEvent evento) {
		
		if(evento.getSource() == btnConsignarCuentaAhorros){
			
			consignarAhorros();
			
		
			
		}
		else if(evento.getSource() == btnConsignarCuentaCorriente ){
			
			
			consignarCorriente ();
		}
		else if(evento.getSource() == btnRetirarCuentaAhorros ){
			
			retirarAhorros ();
			
		}
		else if(evento.getSource() == btnRetirarCuentaCorriente ){
			
			retirarCorriente ();
			
		}
		
		else if(evento.getSource() == btnConsultarSaldoCuentaAhorros ){
			
			txtSaldo.setText(""+unaCuentaAhorros.getSaldo());
		}
		
		/**
		 * Condicional que consulta el saldo de una cuenta corriente
		 */
		else if(evento.getSource() == btnConsultarSaldoCuentaCorriente ){
			
			txtSaldo.setText(""+unaCuentaCorriente.getSaldo());
		}
		
		/**
		 * Condicional que registra al cliente en una cuenta de ahorros
		 */
		
		else if(evento.getSource()==btnRegistrarClienteCuentaAhorros){
			
			registrarClienteAhorros();
			
		}
		
		/**
		 *Condicional que registra al cliente en una cuenta corriente
		 */
		
		else if (evento.getSource()== btnRegistrarClienteCuentaCorriente){
			
			registrarClienteCorriente ();
		}
		
		/**
		 * Condicional que linpia todos los campos de la ventana
		 */
		
		else if(evento.getSource() == btnLimpiar ){
			
			limpiarCampos();
			
			
		}
		
		/**
		 * condicional que cierra la ventana
		 */
		
		else if(evento.getSource() == btnSalir ){
			
			System.exit(0);
			
		}
		
		
	}
	
	/**
	 * Metodo que limpia todos los campos de 
	 * la ventana ( caja de texto), y debuelve el cursor
	 * donde esta el Documento cliente.
	 */
	

	private void limpiarCampos() {
		
		this.txtValor.setText("");
		this.txtSaldo.setText("");
		this.txtNombre.setText("");
		this.txtTelefono.setText("");
		this.txtApellido.setText("");
		this.txtDocumentoCliente.setText("");
		this.txtDocumentoCliente.requestFocus();
		
	}
}
