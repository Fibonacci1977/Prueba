# Page 1

![](https://codigosdeprogramacion.com/wp-content/uploads/2023/01/crud-java-mysql-nw.jpg)

## Tutorial CRUD en Java y MySQL

26 enero, 2023 por [Administrador](https://codigosdeprogramacion.com/author/admin/)

Durante nuestro curso de desarrollo de aplicaciones en Java y MySQL aprendemos a crear un CRUD, que es el acronimo de **C**reate, **R**ead, **U**pdate and **D**elete (Crear, Leer, Actualizar y Borrar), que se usa para referirse a las transacciones básicas en bases de datos.

Administración de datos

Primero aprenderemos a realizar esta aplicación de forma sencilla con [ programación](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/) estructurada para familiarizarnos con el lenguaje de programación Java y la integración de datos de MySQL. Más adelante haremos una aplicación similar pero implementado la arquitectura MVC.

Tabla de contenido



* [Requerimientos](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Requerimientos)
* [Crear base de datos](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Crear_base_de_datos)
* [Crear proyecto](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Crear_proyecto)
* [Diseño de la vista](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Diseno_de_la_vista)
* [Conexión a MySQL](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Conexion_a_MySQL)
  * [Método para conexión](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_para_conexion)
* [Métodos CRUD](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodos_CRUD)
  * [Método del botón para guardar](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_del_boton_para_guardar)
  * [Método del botón para buscar](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_del_boton_para_buscar)
  * [Método del botón para editar](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_del_boton_para_editar)
  * [Método del botón para eliminar](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_del_boton_para_eliminar)
  * [Método del botón limpiar](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Metodo_del_boton_limpiar)
  * Software
* [Ejecutar proyecto CRUD](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Ejecutar_proyecto_CRUD)
* [Bonus](https://codigosdeprogramacion.com/2023/01/26/tutorial-crud-en-java-y-mysql/#Bonus)

### **Requerimientos**

* JDK 8.0 o superior
* MySQL 5.7 o superior
* Connector/J 8.0

_El proyecto se desarrollo con de IDE Apache Netbeans._

### **Crear base de datos**

Aquí la estructura de la base de datos y tabla.

```
CREATE DATABASE IF NOT EXISTS `escuela` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

USE `escuela`;

CREATE TABLE `persona` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `clave` varchar(10) COLLATE utf8mb4_unicode_ci NOT NULL,
  `nombre` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL,
  `domicilio` varchar(200) COLLATE utf8mb4_unicode_ci NOT NULL,
  `telefono` varchar(15) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `correo_electronico` varchar(45) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `fecha_nacimiento` date DEFAULT NULL,
  `genero` varchar(10) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

### **Crear proyecto**

El proyecto lo hemos desarrollado en el IDE **Netbeans** actualmente **Apache Netbeans**. Creamos un proyecto de tipo **Java Application** y desmarcamos la casilla Create Main Class:

Programación

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/1-crud-java-mysql.png" alt="" height="501" width="723"><figcaption></figcaption></figure>

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/2-crud-java-mysql.png" alt="" height="501" width="723"><figcaption></figcaption></figure>

Esto creará un proyecto vacío por lo cual agregaremos un paquete dan clic derecho sobre el nombre del proyecto > New > **Java Package** y no nombramos como **app**.

Dentro de este paquete agregamos un JFrame dando clic derecho sobre el nombre del paquete > New > **JFrame Form** y lo nombramos como **persona**.

La estructura del proyecto se será así:

Administración de datos

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-22.png" alt="" height="150" width="250"><figcaption></figcaption></figure>

### **Diseño de la vista**

Para agregar el diseño de nuestro formulario abrimos el archivo **persona.java** dando doble clic, agregamos el siguiente diseño:

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-23.png" alt="" height="448" width="531"><figcaption></figcaption></figure>

**Descripción de los elementos**

Herramientas de desarrollo

| Elemento   | Texto               | Variable     |
| ---------- | ------------------- | ------------ |
| JLabel     | Clave               |              |
| JLabel     | Nombre              |              |
| JLabel     | Domicilio           |              |
| JLabel     | Telefono            |              |
| JLabel     | Email               |              |
| JLabel     | Fecha de nacimiento |              |
| JLabel     | Genero              |              |
| JTextField |                     | txtClave     |
| JTextField |                     | txtId        |
| JTextField |                     | txtNombre    |
| JTextField |                     | txtDomicilio |
| JTextField |                     | txtTelefono  |
| JTextField |                     | txtEmail     |
| JTextField |                     | txtFecha     |
| JComboBox  |                     | cbxGenero    |
| JButton    | Buscar              | btnBuscar    |
| JButton    | Guarda              | btnGuarda    |
| JButton    | Modifica            | btnModifica  |
| JButton    | Elimina             | btnElimina   |
| JButton    | Limpiar             | btnLimpiar   |

Para el elemento JComboBox ve a la propiedades y en Model agrega las opciones:

Java (lenguaje de programación)

* Selecciona
* Masculino
* Femenino

Puedes agregar más opciones. También puede agregar más elementos al formulario según tus necesidades.

### **Conexión a MySQL**

Para conectar Java con MySQL se necesita un controlador JDBC compatible entre la versión JDK y MySQL. Descargar [Connector/J](https://dev.mysql.com/downloads/connector/j/).

Después de descargar el controlador vamos al proyecto y damos clic derecho en la carpeta **Libraries** y seleccionamos **Add JAR/Folder**, buscamos el controlador **.jar** y lo agregamos.

Teniendo el controlador agregado ya podemos conectarnos a la base de datos de MySQL para esto regresamos al JFrame pero ahora seleccionamos la pestaña source para ver el código fuente del formulario.

Software

#### **Método para conexión**

Dentro del código fuente de la clase persona.java trabajaremos después del constructor que es el método que se llama igual que la clase.

```
public static Connection getConection() {
    Connection con = null;
    String base = "escuela"; //Nombre de la base de datos
    String url = "jdbc:mysql://localhost:3306/" + base; //Direccion, puerto y nombre de la Base de Datos
    String user = "root"; //Usuario de Acceso a MySQL
    String password = "password"; //Password del usuario

    try {
        Class.forName("com.mysql.cj.jdbc.Driver");
        con = DriverManager.getConnection(url, user, password);
    } catch (ClassNotFoundException | SQLException e) {
        System.err.println(e);
    }
    return con;
}
```

### **Métodos CRUD**

Después de realizar la conexión a MySQL crearemos los métodos para las transacciones básicas; Registrar, Leer o Buscar, Modificar y Eliminar. Para estos se necesita implementar eventos de ActionListener la cual se usa para detectar y manejar eventos de acción, como el clic en los botones.

Administración de datos

Podemos activar este eventos de forma automática regresando a la vista diseño y dando doble clic en los botones o dando clic derecho sobre el botón > Events > Action > actionPerformed.

Antes de agregar el código a los botón crearemos un método que elimine el contenido de las cajas de texto (JTextField).

```
private void limpiarCajas() {
    txtClave.setText(null);
    txtNombre.setText(null);
    txtDomicilio.setText(null);
    txtTelefono.setText(null);
    txtEmail.setText(null);
    txtFecha.setText(null);
    cbxGenero.setSelectedIndex(0);
}
```

#### **Método del botón para guardar**

```
private void btnGuardaActionPerformed(java.awt.event.ActionEvent evt) {                                          

    Connection con;

    try {
        con = getConection();
        ps = con.prepareStatement("INSERT INTO persona (clave, nombre, domicilio, telefono, correo_electronico, fecha_nacimiento, genero) VALUES(?,?,?,?,?,?,?) ");
        ps.setString(1, txtClave.getText());
        ps.setString(2, txtNombre.getText());
        ps.setString(3, txtDomicilio.getText());
        ps.setString(4, txtTelefono.getText());
        ps.setString(5, txtEmail.getText());
        ps.setDate(6, Date.valueOf(txtFecha.getText()));
        ps.setString(7, cbxGenero.getSelectedItem().toString());

        int res = ps.executeUpdate();

        if (res > 0) {
            JOptionPane.showMessageDialog(null, "Persona Guardada");
        } else {
            JOptionPane.showMessageDialog(null, "Error al Guardar persona");
        }
			
	limpiarCajas();
        con.close();

    } catch (HeadlessException | SQLException e) {
        System.err.println(e);
    }
}
```

#### **Método del botón para buscar**

```
private void btnBuscarActionPerformed(java.awt.event.ActionEvent evt) {

    Connection con;

    try {
        con = getConection();
        ps = con.prepareStatement("SELECT * FROM persona WHERE clave = ?");
        ps.setString(1, txtClave.getText());

        rs = ps.executeQuery();

        if (rs.next()) {
            txtId.setText(rs.getString("id"));
            txtNombre.setText(rs.getString("nombre"));
            txtDomicilio.setText(rs.getString("domicilio"));
            txtTelefono.setText(rs.getString("telefono"));
            txtEmail.setText(rs.getString("correo_electronico"));
            txtFecha.setText(rs.getString("fecha_nacimiento"));
            cbxGenero.setSelectedItem(rs.getString("genero"));
        } else {
            JOptionPane.showMessageDialog(null, "No existe una persona con la clave");
            limpiarCajas();
        }

    } catch (HeadlessException | SQLException e) {
        System.err.println(e);
    }
}
```

#### **Método del botón para editar**

```
private void btnModificaActionPerformed(java.awt.event.ActionEvent evt) {

    Connection con;

    try {
        con = getConection();
        ps = con.prepareStatement("UPDATE persona SET clave=?, nombre=?, domicilio=?, telefono=?, correo_electronico=?, fecha_nacimiento=?, genero=? WHERE id=?");
        ps.setString(1, txtClave.getText());
        ps.setString(2, txtNombre.getText());
        ps.setString(3, txtDomicilio.getText());
        ps.setString(4, txtTelefono.getText());
        ps.setString(5, txtEmail.getText());
        ps.setDate(6, Date.valueOf(txtFecha.getText()));
        ps.setString(7, cbxGenero.getSelectedItem().toString());
        ps.setString(8, txtId.getText());

        int res = ps.executeUpdate();

        if (res > 0) {
            JOptionPane.showMessageDialog(null, "Persona Modificada");
        } else {
            JOptionPane.showMessageDialog(null, "Error al Modificar persona");
        }
        limpiarCajas();
        con.close();

    } catch (HeadlessException | SQLException e) {
        System.err.println(e);
    }
}
```

#### **Método del botón para eliminar**

```
private void btnEliminaActionPerformed(java.awt.event.ActionEvent evt) {

    Connection con;

    try {
        con = getConection();
        ps = con.prepareStatement("DELETE FROM persona WHERE id=?");
        ps.setInt(1, Integer.parseInt(txtId.getText()));

        int res = ps.executeUpdate();

        if (res > 0) {
            JOptionPane.showMessageDialog(null, "Persona Eliminada");
        } else {
            JOptionPane.showMessageDialog(null, "Error al eliminar persona");
        }
        limpiarCajas();
        con.close();

    } catch (HeadlessException | NumberFormatException | SQLException e) {
        System.err.println(e);
    }
}
```

#### **Método del botón limpiar**

```
private void btnLimpiarActionPerformed(java.awt.event.ActionEvent evt) {                                           
    limpiarCajas();
}
```

Como instrucción adicional podemos hacer que el campo de texto para guardar temporalmente el ID del registro no sea visible. Para esto agregamos la propiedad **setVisible(false)** a la variable **txtId**, esto será en el método constructor después de iniciar los componentes.

Java (lenguaje de programación)

```
public persona() {
    initComponents();
    txtId.setVisible(false);
}
```

### **Ejecutar proyecto CRUD**

Para ejecutar el proyecto damos clic derecho dentro de la clase y seleccionar **Run File** para ejecutar el proyecto.

**Resultado**

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-24.png" alt="" height="415" width="493"><figcaption></figcaption></figure>

Puedes crear tu propio diseño, quitar o agregar campos al formulario y adaptarlo a tus necesidades.

### **Bonus**

Si quieres una explicación más detallada sobre este proyecto puedes ver el siguiente vídeo:

{% embed url="https://youtu.be/65WgYJ5neMM?si=WySurJlhXfJMTX2v" %}

También puedes ver y descargar el proyecto desde GitHub: [https://github.com/mroblesdev/CRUD-Java-MySQL](https://github.com/mroblesdev/CRUD-MVC-Java-MySQL)

[Crear una base de datos de MySQL en cPanel](https://codigosdeprogramacion.com/2023/01/05/crear-una-base-de-datos-de-mysql-en-cpanel/)

[Tutorial CRUD MVC en Java y MySQL](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/)

![](https://codigosdeprogramacion.com/wp-content/uploads/2023/01/CRUD-MVC-small.jpg)

## Tutorial CRUD MVC en Java y MySQL



En nuestro canal de Youtube tenemos un vídeo donde desarrollamos un programa en Java realizando las principales transacciones a base de datos usando la arquitectura Modelo Vista Controlador (MVC). Para el almacenamiento de información se utiliza MySQL, en un tabla de productos.

Administración de datos

Tabla de contenido



* [Requerimientos](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Requerimientos)
* [Crear base de datos](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Crear_base_de_datos)
* [Crear proyecto](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Crear_proyecto)
* [Conexión a MySQL](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Conexion_a_MySQL)
  * [Clase Conexion](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Clase_Conexion)
  * [Mapeo de datos](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Mapeo_de_datos)
* [Métodos CRUD](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Metodos_CRUD)
* [Diseño de la vista](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Diseno_de_la_vista)
* [Controlador](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Controlador)
* [Ejecutar proyecto CRUD](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Ejecutar_proyecto_CRUD)
* [Bonus](https://codigosdeprogramacion.com/2023/01/31/tutorial-crud-mvc-en-java-y-mysql/#Bonus)

### **Requerimientos**

* JDK 8.0 o superior
* MySQL 5.7 o superior
* Connector/J 8.0

El proyecto se desarrollo en Apache Netbeans.

### **Crear base de datos**

Aquí la estructura de la base de datos y tabla.

Java (lenguaje de programación)

| CREATE DATABASE IF NOT EXISTS \`tienda\` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4\_unicode\_ci; |
| ---------------------------------------------------------------------------------------------------- |
| USE \`tienda\`;                                                                                      |
| CREATE TABLE \`producto\` (                                                                          |
| \`id\` int NOT NULL AUTO\_INCREMENT,                                                                 |
| \`codigo\` varchar(20) COLLATE utf8mb4\_unicode\_ci NOT NULL,                                        |
| \`nombre\` varchar(50) COLLATE utf8mb4\_unicode\_ci NOT NULL,                                        |
| \`precio\` decimal(10,2) NOT NULL,                                                                   |
| \`cantidad\` int NOT NULL,                                                                           |
| PRIMARY KEY(id)                                                                                      |
| ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4\_unicode\_ci;                                |



### **Crear proyecto**

El proyecto lo hemos desarrollado en el IDE **Netbeans** actualmente **Apache Netbeans**. Creamos un proyecto de tipo **Java Application** y agregamos los siguientes paquetes, clases y formulario:

* Paquete Controlador
  * Clase CtrlProducto.java
* Paquete Modelo
  * Clase Conexion.java
  * Clase ConsultasProducto.java
  * Clase Producto.java
* Paquete Vista
  * JFrame frmProducto.java
* Paquete crudmvc (paquete predefinido)
  * Clase CRUDMVC.java (clase principal)

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-15.png" alt="" height="256" width="242"><figcaption></figcaption></figure>

Hemos creado el proyecto con nombre **CRUDMVC** por lo cual el nombre del paquete predefinido y clase principal será el nombre del proyecto.

Administración de datos

### **Conexión a MySQL**

Para conectar Java con MySQL se necesita un controlador JDBC compatible entre la versión JDK y MySQL. Descargar [Connector/J](https://dev.mysql.com/downloads/connector/j/).

Después de descargar el controlador vamos al proyecto y damos clic derecho en la carpeta **Libraries** y seleccionamos **Add JAR/Folder**, buscamos el controlador **.jar** y lo agregamos.

#### **Clase Conexion**

Dentro del paquete Modelo abrimos la clase Conexion.java y agregamos el siguiente código:

| package Modelo;                                         |
| ------------------------------------------------------- |
|                                                         |
| import java.sql.Connection;                             |
| import java.sql.DriverManager;                          |
| import java.sql.SQLException;                           |
|                                                         |
| public class Conexion {                                 |
|                                                         |
| Connection con = null;                                  |
|                                                         |
| String base = "tienda";                                 |
| String url = "jdbc:mysql://localhost:3306/" + base;     |
| String user = "root";                                   |
| String password = "password";                           |
|                                                         |
| public Connection getConexion() {                       |
|                                                         |
| try {                                                   |
| Class.forName("com.mysql.cj.jdbc.Driver");              |
| con = DriverManager.getConnection(url, user, password); |
| } catch (ClassNotFoundException \| SQLException e) {    |
| System.err.println(e);                                  |
| }                                                       |
| return con;                                             |
| }                                                       |
| }                                                       |



Esta clase nos permite conectarnos a MySQL, debes cambiar los valores de las variables base, url, user y password correspondientes a tus datos que configuraste en la instalación de MySQL.

Java (lenguaje de programación)

#### **Mapeo de datos**

Para transformar los atributos de la tabla producto a objetos y usarlos con facilidad necesitamos hacer un mapeo dentro de la clase Producto.java que está en el paquete Modelo. Definimos los atributos generando sus getters y setters.

| package Modelo;                         |
| --------------------------------------- |
|                                         |
| public class Producto {                 |
|                                         |
| private int id;                         |
| private String codigo;                  |
| private String nombre;                  |
| private Double precio;                  |
| private int cantidad;                   |
|                                         |
| public int getId() {                    |
| return id;                              |
| }                                       |
|                                         |
| public void setId(int id) {             |
| this.id = id;                           |
| }                                       |
|                                         |
| public String getCodigo() {             |
| return codigo;                          |
| }                                       |
|                                         |
| public void setCodigo(String codigo) {  |
| this.codigo = codigo;                   |
| }                                       |
|                                         |
| public String getNombre() {             |
| return nombre;                          |
| }                                       |
|                                         |
| public void setNombre(String nombre) {  |
| this.nombre = nombre;                   |
| }                                       |
|                                         |
| public Double getPrecio() {             |
| return precio;                          |
| }                                       |
|                                         |
| public void setPrecio(Double precio) {  |
| this.precio = precio;                   |
| }                                       |
|                                         |
| public int getCantidad() {              |
| return cantidad;                        |
| }                                       |
|                                         |
| public void setCantidad(int cantidad) { |
| this.cantidad = cantidad;               |
| }                                       |
| }                                       |



### **Métodos CRUD**

Después de realizar la conexión a MySQL y mapear los datos crearemos los métodos para las transacciones básicas; Registrar, Leer o Buscar, Modificar y Eliminar. Dentro del paquete Modelo abrimos la clase ConsultasProducto.java y agregamos el siguiente código:

Administración de datos

| package Modelo;                                                                          |
| ---------------------------------------------------------------------------------------- |
|                                                                                          |
| import java.sql.Connection;                                                              |
| import java.sql.PreparedStatement;                                                       |
| import java.sql.ResultSet;                                                               |
| import java.sql.SQLException;                                                            |
|                                                                                          |
| public class ConsultasProducto extends Conexion {                                        |
|                                                                                          |
| public boolean registrar(Producto pro) {                                                 |
| PreparedStatement ps = null;                                                             |
| Connection con = getConexion();                                                          |
|                                                                                          |
| String sql = "INSERT INTO producto (codigo, nombre, precio , cantidad) VALUES(?,?,?,?)"; |
|                                                                                          |
| try {                                                                                    |
| ps = con.prepareStatement(sql);                                                          |
| ps.setString(1, pro.getCodigo());                                                        |
| ps.setString(2, pro.getNombre());                                                        |
| ps.setDouble(3, pro.getPrecio());                                                        |
| ps.setInt(4, pro.getCantidad());                                                         |
| ps.execute();                                                                            |
| return true;                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| return false;                                                                            |
| } finally {                                                                              |
| try {                                                                                    |
| con.close();                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| }                                                                                        |
| }                                                                                        |
| }                                                                                        |
|                                                                                          |
| public boolean modificar(Producto pro) {                                                 |
| PreparedStatement ps = null;                                                             |
| Connection con = getConexion();                                                          |
|                                                                                          |
| String sql = "UPDATE producto SET codigo=?, nombre=?, precio=?, cantidad=? WHERE id=? "; |
|                                                                                          |
| try {                                                                                    |
| ps = con.prepareStatement(sql);                                                          |
| ps.setString(1, pro.getCodigo());                                                        |
| ps.setString(2, pro.getNombre());                                                        |
| ps.setDouble(3, pro.getPrecio());                                                        |
| ps.setInt(4, pro.getCantidad());                                                         |
| ps.setInt(5, pro.getId());                                                               |
| ps.execute();                                                                            |
| return true;                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| return false;                                                                            |
| } finally {                                                                              |
| try {                                                                                    |
| con.close();                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| }                                                                                        |
| }                                                                                        |
| }                                                                                        |
|                                                                                          |
| public boolean eliminar(Producto pro) {                                                  |
| PreparedStatement ps = null;                                                             |
| Connection con = getConexion();                                                          |
|                                                                                          |
| String sql = "DELETE FROM producto WHERE id=? ";                                         |
|                                                                                          |
| try {                                                                                    |
| ps = con.prepareStatement(sql);                                                          |
| ps.setInt(1, pro.getId());                                                               |
| ps.execute();                                                                            |
| return true;                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| return false;                                                                            |
| } finally {                                                                              |
| try {                                                                                    |
| con.close();                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| }                                                                                        |
| }                                                                                        |
| }                                                                                        |
|                                                                                          |
| public boolean buscar(Producto pro) {                                                    |
| PreparedStatement ps = null;                                                             |
| ResultSet rs = null;                                                                     |
| Connection con = getConexion();                                                          |
|                                                                                          |
| String sql = "SELECT \* FROM producto WHERE codigo=? ";                                  |
|                                                                                          |
| try {                                                                                    |
| ps = con.prepareStatement(sql);                                                          |
| ps.setString(1, pro.getCodigo());                                                        |
| rs = ps.executeQuery();                                                                  |
|                                                                                          |
| if (rs.next()) {                                                                         |
| pro.setId(Integer.parseInt(rs.getString("id")));                                         |
| pro.setCodigo(rs.getString("codigo"));                                                   |
| pro.setNombre(rs.getString("nombre"));                                                   |
| pro.setPrecio(Double.parseDouble(rs.getString("precio")));                               |
| pro.setCantidad(Integer.parseInt(rs.getString("cantidad")));                             |
| return true;                                                                             |
| }                                                                                        |
| return false;                                                                            |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| return false;                                                                            |
| } finally {                                                                              |
| try {                                                                                    |
| con.close();                                                                             |
| } catch (SQLException e) {                                                               |
| System.err.println(e);                                                                   |
| }                                                                                        |
| }                                                                                        |
| }                                                                                        |
| }                                                                                        |

Esta clase hereda de la clase Conexion.java, los métodos reciben un objeto de tipo Producto.

Software

### **Diseño de la vista**

Dentro del paquete Vista abrimos el JFrame frmProducto y agregamos el siguiente diseño:

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-16.png" alt="" height="332" width="402"><figcaption></figcaption></figure>

**Descripción de los elementos**

Java (lenguaje de programación)

| **Elemento** | **Texto** | **Variable** | **Acceso**  |
| ------------ | --------- | ------------ | ----------- |
| JLabel       | Código    | Predefinida  | Predefinida |
| JLabel       | Nombre    | Predefinida  | Predefinida |
| JLabel       | Precio    | Predefinida  | Predefinida |
| JLabel       | Cantidad  | Predefinida  | Predefinida |
| JTextField   |           | txtCodigo    | public      |
| JTextField   |           | txtNombre    | public      |
| JTextField   |           | txtPrecio    | public      |
| JTextField   |           | txtCantidad  | public      |
| JTextField   |           | txtId        | public      |
| JButton      | Buscar    | btnBuscar    | public      |
| JButton      | Guardar   | btnGuardar   | public      |
| JButton      | Modificar | btnModificar | public      |
| JButton      | Eliminar  | btnEliminar  | public      |
| JButton      | Limpiar   | btnLimpiar   | public      |

Los elementos que hemos agregamos con acceso publico serán necesarios para acceder a ellos desde el controlador.

### **Controlador**

Para que la vista pueda interactuar con el modelo usaremos la clase CtrlProducto.java que se encuentra dentro del paquete Controlador. Con esto terminas aplicando la arquitectura MVC.

Esta clase implementa la interfaz ActionListener la cual se usa para detectar y manejar eventos de acción, como el clic en los botones.

| package Controlador;                                                                   |
| -------------------------------------------------------------------------------------- |
|                                                                                        |
| import Modelo.ConsultasProducto;                                                       |
| import Modelo.Producto;                                                                |
| import Vista.frmProducto;                                                              |
| import java.awt.event.ActionEvent;                                                     |
| import java.awt.event.ActionListener;                                                  |
| import javax.swing.JOptionPane;                                                        |
|                                                                                        |
| public class CtrlProducto implements ActionListener {                                  |
|                                                                                        |
| private final Producto modelo;                                                         |
| private final ConsultasProducto consultas;                                             |
| private final frmProducto vista;                                                       |
|                                                                                        |
| public CtrlProducto(Producto modelo, ConsultasProducto consultas, frmProducto vista) { |
| this.modelo = modelo;                                                                  |
| this.consultas = consultas;                                                            |
| this.vista = vista;                                                                    |
| this.vista.btnGuardar.addActionListener(this);                                         |
| this.vista.btnModificar.addActionListener(this);                                       |
| this.vista.btnEliminar.addActionListener(this);                                        |
| this.vista.btnLimpiar.addActionListener(this);                                         |
| this.vista.btnBuscar.addActionListener(this);                                          |
| }                                                                                      |
|                                                                                        |
| public void iniciar() {                                                                |
| vista.setTitle("Productos");                                                           |
| vista.setLocationRelativeTo(null);                                                     |
| vista.txtId.setVisible(false);                                                         |
| }                                                                                      |
|                                                                                        |
| @Override                                                                              |
| public void actionPerformed(ActionEvent e) {                                           |
|                                                                                        |
| if (e.getSource() == vista.btnGuardar) {                                               |
| modelo.setCodigo(vista.txtCodigo.getText());                                           |
| modelo.setNombre(vista.txtNombre.getText());                                           |
| modelo.setPrecio(Double.parseDouble(vista.txtPrecio.getText()));                       |
| modelo.setCantidad(Integer.parseInt(vista.txtCantidad.getText()));                     |
|                                                                                        |
| if (consultas.registrar(modelo)) {                                                     |
| JOptionPane.showMessageDialog(null, "Registro Guardado");                              |
| limpiar();                                                                             |
| } else {                                                                               |
| JOptionPane.showMessageDialog(null, "Error al Guardar");                               |
| limpiar();                                                                             |
| }                                                                                      |
| }                                                                                      |
|                                                                                        |
| if (e.getSource() == vista.btnModificar) {                                             |
| modelo.setId(Integer.parseInt(vista.txtId.getText()));                                 |
| modelo.setCodigo(vista.txtCodigo.getText());                                           |
| modelo.setNombre(vista.txtNombre.getText());                                           |
| modelo.setPrecio(Double.parseDouble(vista.txtPrecio.getText()));                       |
| modelo.setCantidad(Integer.parseInt(vista.txtCantidad.getText()));                     |
|                                                                                        |
| if (consultas.modificar(modelo)) {                                                     |
| JOptionPane.showMessageDialog(null, "Registro Modificado");                            |
| limpiar();                                                                             |
| } else {                                                                               |
| JOptionPane.showMessageDialog(null, "Error al Modificar");                             |
| limpiar();                                                                             |
| }                                                                                      |
| }                                                                                      |
|                                                                                        |
| if (e.getSource() == vista.btnEliminar) {                                              |
| modelo.setId(Integer.parseInt(vista.txtId.getText()));                                 |
|                                                                                        |
| if (consultas.eliminar(modelo)) {                                                      |
| JOptionPane.showMessageDialog(null, "Registro Eliminado");                             |
| limpiar();                                                                             |
| } else {                                                                               |
| JOptionPane.showMessageDialog(null, "Error al Eliminar");                              |
| limpiar();                                                                             |
| }                                                                                      |
| }                                                                                      |
|                                                                                        |
| if (e.getSource() == vista.btnBuscar) {                                                |
| modelo.setCodigo(vista.txtCodigo.getText());                                           |
|                                                                                        |
| if (consultas.buscar(modelo)) {                                                        |
| vista.txtId.setText(String.valueOf(modelo.getId()));                                   |
| vista.txtCodigo.setText(modelo.getCodigo());                                           |
| vista.txtNombre.setText(modelo.getNombre());                                           |
| vista.txtPrecio.setText(String.valueOf(modelo.getPrecio()));                           |
| vista.txtCantidad.setText(String.valueOf(modelo.getCantidad()));                       |
|                                                                                        |
| } else {                                                                               |
| JOptionPane.showMessageDialog(null, "No se encontro registro");                        |
| limpiar();                                                                             |
| }                                                                                      |
| }                                                                                      |
|                                                                                        |
| if (e.getSource() == vista.btnLimpiar) {                                               |
| limpiar();                                                                             |
| }                                                                                      |
| }                                                                                      |
|                                                                                        |
| public void limpiar() {                                                                |
| vista.txtId.setText(null);                                                             |
| vista.txtCodigo.setText(null);                                                         |
| vista.txtNombre.setText(null);                                                         |
| vista.txtPrecio.setText(null);                                                         |
| vista.txtCantidad.setText(null);                                                       |
| }                                                                                      |
| }                                                                                      |

### **Ejecutar proyecto CRUD**

Para ejecutar el proyecto se requiere una clase principal para llamar al controlador y este a su vez enlazar la vista con el modelo. La clase CRUDMVC.java se encuentra dentro del paquete predefinido que comúnmente tiene el mismo nombre del proyecto.

| package crudmvc;                                      |
| ----------------------------------------------------- |
|                                                       |
| import Controlador.CtrlProducto;                      |
| import Modelo.ConsultasProducto;                      |
| import Modelo.Producto;                               |
| import Vista.frmProducto;                             |
|                                                       |
| public class CRUDMVC {                                |
|                                                       |
| public static void main(String\[] args) {             |
|                                                       |
| Producto mod = new Producto();                        |
| ConsultasProducto modC = new ConsultasProducto();     |
| frmProducto frm = new frmProducto();                  |
|                                                       |
| CtrlProducto ctrl = new CtrlProducto(mod, modC, frm); |
| ctrl.iniciar();                                       |
| frm.setVisible(true);                                 |
| }                                                     |
| }                                                     |



Después de agregar el código anterior podemos dar clic derecho dentro de la clase y seleccionar **Run File** para ejecutar el proyecto.

**Resultado**

<figure><img src="https://codigosdeprogramacion.com/wp-content/uploads/2023/01/image-18.png" alt="" height="338" width="450"><figcaption></figcaption></figure>

Puedes crear tu propio diseño, quitar o agregar campos al formulario y adaptarlo a tus necesidades.

### **Bonus**

Si quieres una explicación más detallada sobre este proyecto puedes ver el siguiente vídeo:

{% embed url="https://youtu.be/0w-2Ik-VPwU?si=YxVN5ZIRtVt7pbRP" %}

También puedes ver y descargar el proyecto desde GitHub: [https://github.com/mroblesdev/CRUD-MVC-Java-MySQL](https://github.com/mroblesdev/CRUD-MVC-Java-MySQL)
