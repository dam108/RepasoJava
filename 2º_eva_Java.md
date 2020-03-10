# Repaso para el examen de la segunda evaluación de Java

# Herencia
Se crea una clase padre o super clase:
``` java
class Alumno {
  public String nombre;
  public String DNI;
  public int faltas;
  
  Alumno(){};
  Alumno(String n, String D){
    this.nombre = n;
    this.DNI = D;
    faltas = 0
  }
  public void setNombre (String n){this.nombre = n;}
  public void setDNI (String D){this.DNI = D;}
  public void setFaltas (){faltas = 0;}
}
```
Ahora se crean las subclases o clases hijas:
``` java
class Alumnos extends Alumno { // utilizamos la notacion extends para indicar que esta hereda de una superclase
  public int telefono;
  
  AlumnoESO (String nom, String dn, int tel){
    super(nom, dn); // lo primero siempre es pasar los parametros a la superclase
    this.telefono = tel; // este atributo solo pertenece a la sub-clase
  }
  public void setTelefono (int t){this.telefono = t;} // estos metodos solo pertenecesn  a la sub-clase
  public void nuevaFalta (int sesiones){
    this.faltas += sesiones;
    System.out.println("Falta registrada. Llmamr a "+ this.telefono;
    if(this.faltas > 30) System.out.println("Llamar a asuntos sociales");
  }
} 
```
> si desde una clase hija queremos llamar a un metodo de la clase padre podemos utilizar la notacion super.metodoDelPadre();

> Para instanciar clases heredadas es como siempre AlumnoEso alumEso1 = new AlumnoESO("Pedro Gomez", "1252364N", 981526498);

> si queremos impedir la herencia (que no se puedan derivar clases hijas de las hijas ) le asignamos el modificador final

Ejemplo: 
```java
public final class AlumnosESO extendes Alumno{}
```
> Desde las clases hijas podemos utlizar los metodos de la superclase , utilizar metodos propios o sobreescribir metodos de la superclase.

> Para identificar un metodo sobreescrito nos fijamos en la anotacion @Override

> todas las clases son hijas de la superclase por exelencia Object

__________________________________________________________________________________

# Metodos Comunes

## getClass
Devuelve la clase del objeto sobre el que se llama. 
```java
obj.getClass().getClass().getSimpleName(); // pedimos el nombre concreto de las clase , sin el paquete
```

### Operador instanceof
Nos permite preguntar el tipo de variable

> Devuelve un valor boolean indicando si la instancia pertenece a esa clase o no, tambien devuelve true para todas las clases ancestro.

```java
if (a3 instanceof AlumnoCiclos)
  System.out.println (((AlumnoCiclos).a3).Empresa); // si es una instancia de alumnoCiclos ejecutamos el metodo Empresa()
```
Notas:
Si la variable a2 es una instancia de AlumnosCiclos
a2 instanceof AlumnosCiclos -- Se evalua como true por que es la misma
a2 instanceof Alumno -- se evalua como true por que alumno es el padre y pertenece en parte
a2 instanceof AlumnoESO -- se evalua como false por que solo es un hermano y no tiene nada que ver.

## Getters y Setters
son métodos de acceso público y se usan para dar acceso a los atributos que definimos de acceso private.

Ejemplo: 
```java
public class Empleado {
  private int id;
  private String nombre;
  
  public int getID(){ return this.id; }
  public void setID(int id){ this.id = id; }
  public String getNombre(){ return this.nombre; }
  public void setNombre(String nom){ this.nombre = nom; }
}
```

## toString
> Se utiliza para convertir a String cualquier texto, este método esta definido por la clase Object

> El metodo Object.toString() esta Sobrescrito por muchas clases como por ejemplo LocalDateTime o ArrayList por eso podemos imprimir directamente una fecha o un Arraylist

> Si queres usarlo en nuestras classes deberiamos redefinirlo 

Ejemplo:
```java
@Override
public String toString () {
  long edad = 19;
  String txt = String.format("ID:%d %s %d años", this.id, this.nombre, edad);
  return txt
}
```
Al Ejecutar 
```java 
AlumnoESO.toString();
```
Se mostraria : ID:10 Pedro Gomez 19 añaos

## equals
Es un caso similar al de toString(), tambien esta definido sobre la clase Object y si lo queremos usar tienes unos valores predefinidos, en la mayoria de los casos nos vale pero lo mejor es sobreescribirlo para adaptarlo a nuestras necesidades

> Nos va a permitir indicarle los parametros que queremos que utlize para comparar si un objeto es igual a otro.

> si probamos en una de  nuestras clases a usarlo, al no estar sobreescrito el resultado será incorrecto por lo tanto para comparar objetos debemos sobreescribir el metodo

Ejemplo en el que queremos compara dos objetos segun su dni:
```java
@Override
public boolean equals(Object a){
  if (a == null) return false;
  if (a == this) return true;
  if (!(a instance of Alumno)) return false;
  Alumno o = (Alumno) a; // Creamos una variable Alumno para igual al Casting del objeto pasado
  if (o.dni.equals(this.dni)) return true; // si los dnis son iguales devolvemos true
  return false;
}

```
> De este modo ya podemos utilizar desde nuestro Main metodos como indexof o contains en nuestros ArrayLists para que nos diga la posiocion o si encuentra o no el objeto pasado dentro de ArrayList

Ejemplo:
```java
Alumno b = new Alumno ("79336549N", "ana"); // creamos un objeto para comparar
pos = instituto.indexOf(b); // usamos indeOf para buscar su posicion 
if (pos != -1 ) System.out.println("Encontrado"); // si lo encontramos imprimimos el aviso
```
## hascode
este metodo se utiliza en vez del equals en determinadas ocasiones asi que si lo necesitamos deberiamos sobreescribirlo 

## clone
Para copiar objetos pasa algo parecido como con la comparación , deberiamos sobreescribirlo para poder copiar objetos

Ejemplo: 
```java
@Override
public Object clone() throws CloneNotSupportedException{
  Object clone = null;
  try { clone = super.clone();}
    catch (cloneNotSupportedException e) {}
    return clone;
}
```

# Polimorfismo
Consiste en guardar en variables o ArrayLists de tipo padre objetos de tipo hijo.

Ejemplo: 
```
Alumno alumno1 = new AlumnoESO("796584122N", "ana");

o

ArrayList<Alumno> instituto = new ArrayList<>();

instituto.add(new AlumnoESO("796584122N", "ana");
instituto.add(new AlumnoESO("896524123N", "pedro");
instituto.add(new AlumnoCiclos("896524123N", "pedro");
```
> El problema es que si queremos mostrar o usar el contenido de las variables o ArrayLists polimorficos necesitamos hacer un casteo de tipo Padre a tipo hijo

Ejemplo para imprimir el contenido de la variable alumno1:
```java
System.out.println ( (AlumnoESO)alumno1 );
```
> Esto se aplica para cualquier otra cosa como por ejemplo utilizar metodos en los objetos que contiene el ArrayList, modificar el objeto que contiene la variable, nunca vamos a poder acceder al objeto y usarlo si no casteamos primero

> Cuando no sabemos de que tipo es el objeto podemos utilizar una cadena de if's con todas las posiblidades

Ejemplo para utlizar el metdo empresa de AlumnoCiclo solo si el objeto es de ese tipo:
```
if (alumno1 instanceof AlumnoCiclos)
  ((AlumnoCiclos)alumno1).Empresa();
if (alumno1 instanceof AlumnoESO)
  System.out.println("Este alumno no tiene el metodo empresa");
```
> Para los ArrayList polimorficos esto se utliza dentro de un bucle for o for each, asi comprueba todos los objetos del ArrayList uno por uno y si es AlumnoClicos ejecuta el metodo empresa() en el.

Nota: Recordatorio for each
```java
for (Alumno x: instituto){
  if (x instanceof AlumnoCiclos)
  ((AlumnoCiclos) x).Empresa();
}
```
## Sobre carga de métodos (overload)
Consiste en crear varios metodos en la misma clase con el mismo nombre y distinto codigo y según que parametros se les pase utilizas un metodo o otro.

Ejemplo:
```java
public void sumar (int a, int b){
  int suma = a + b;
  System.out.println("la suma es: "+suma);
}

public void sumar (double x, double y){
  double suma = x + y;
  System.out.println("la suma es: "+suma);
}












