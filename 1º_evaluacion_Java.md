# Recopilación de todo el contenido de la primera evaluación de java para preparar el examen.
```java
package pruebas;

public class ChuletaRepaso {
    //variables globales
    public static String global = "variable global"; 
    
    public static void main(String[] args) {

        /* TIPOS DE VARIABLES */
        // Enteros
        byte n1 = 8;
        short n2 = 16;
        int n3 = 32;
        long n4 = 64;
        // punto decimal
        double n5 = 64.0;
        float n6 = 32.0f;
        // caracteres
        char letra = 'a';
        // booleanos
        boolean verdadero = true;
        boolean falso = false;
        // strings
        String cadena = "aeiou";
        String cadena2 = new String("aeiou");
        
        /* OPERADORES */
        /* 
         * Suma +
         * Resta -
         * Multiplicación *
         * Division /
         * Incremento ++
         * Decremento --
         * Suma y asignación +=
         * Resta y asignacion -=
         * Multiplicación y asignación *=
         * División y asignacion /=
         * Móduloi (resto) %
         * Módulo y asignación %=
        */
        
        /* OPERADORES LOGICOS
        * Menos <
        * Menor o igual <=
        * Mayor >
        * Mayor o igual >=
        * Igualdad ==
        * Diferente !=
        * AND &&
        * OR ||
        *
        * if ( denom != 0 && num / denom > 10 )
        */
        
        /* CASTING
        * double res = (double) 5 / 2
        * double res = 5 / (double) 2
        * double res = 5 / 2.0
        * double res = 5d / 2
        * double res = (double) x / y 
        * double res = x / (double) y
        */
        
        /* ENTRADA POR CONSOLA
        * java.util.Scanner
        * Scanner teclado = new Scanner(System.in);
        * System.out.println("Introduce numero "); 
        * int numero = tecldo.nextInt();
        * TIPOS
        * .nextLine();
        * .nextFloat();
        * .nextDouble();
        * .next().charAt(0);
        *
        */
        
       /* CONDICIONES
        * if(condicion){ sentencia);
        * else if (condicion2) {sentencia2};
        * else sentencia3
        *
        * if (exp == true) es iugal eque if(exp)
        * if (exp ==  false) es igual que if (!exp)
        *
        *
        * switch (expresion){
        *    case 1: sentencia de sentencias; break;
        *    case 2: sentencia de sentencias; break;
        *    case 3: sentencia de sentencias; break;
        *    case 4: sentencia de sentencias; break;
        *   default: secuencia de sentencias por omision
        */
        
       /* OPERADOR ? 
       * variable = condicion ? expresionTrue : expresionFalse;
       */
       
        /* BUCLES
       * 
       * while (condicion){
       *     // cuerpo del ciclo
       *  }
       * 
       * acumulador = acumulador + incremento;
       * acumulador += incremento;
       *  
       * contador = contador + 1;
       * contador++;
       * 
       * do{
       *    // sentencia que se va ejecutar como minimo una vez
       * } while(condicion);
       * 
       * for (int i = 0; i < num; i++)
       * 
       * for (int i = 0; i < num; i++){
       *    for (int j = 0; j < num; j++)
       * }
       */
        
        /* SENTENCIAS DE SALTO
        *
        * break
        * contine
        * return
        *
        */
        
        /* FLAG / BANDERA
        * 
        * boolean flag = false;
        * 
        * if (condicion) flag = true;
        * 
        * if(flag) sentencia;
        * 
        */
        
        /* CADENAS */
        
        // crear cadenas
        String cad = "Hola mundo";
        String cad2 = new String("Hola");
        
        // longitud de una cadena
        int longitud = cad.length();
        
        // metodos mas usados
        String mayusculas = cad.toUpperCase();
        String minusculas = cad.toLowerCase();
        String subcadena = cad.substring(0,5 );// eso saca una subcadena desde la posicion 0 hasta la 5-1
        cad.equals(cad2); // comprueba si las cadenas son iguales.
        /* INDEX OF para buscar si esta lo pasado dentro de una cadena
        * int pos = cad1.indexOf('x');
        * pos = cad1.indexOf('x', posIni);
        * pos = cad1.indexOf('texto');
        * pos = cad1.indexOf('texto', posIni);
        */
        char letra1 = cad.charAt(3); // saca el caracter en la posicion 3 de la cadena
        String nueva = cad.replace("barco", "coche"); // remplaza todas las palabras barco de la cadena por la palabra coche
        String original = "mi numero es 900.125.987";
        String nueva2 = original.replaceAll("[0-9]", "X"); // replazaria el numero 900.125.987 por XXX.XXX.XXX
        
        /* CONVERTIR TIPOS DE CADENAS Y/O A CADENAS */
        String cad4 = String.valueOf(123); // crear una cadena a partir de un tipo primitivo.
        
        String cad5 = Integer.toBinaryString(253); // devuelve una cadena con el numero pasado a binario
        String cad6 = Integer.toString(255, 16); // se le pasa un numero y una base y devuelve una cadena con el numero pasado a esa base ( ejempl ester sir FF hexadecimal)
        
        int numero1 = Integer.parseInt("10"); // pasa a entero
        float numero2 = Float.parseFloat("20"); // pasa a float
        double numero3 = Double.parseDouble("30.50"); // pasa a doble
                
        // concatenar
        System.out.println(cad+" "+cad2);
        System.out.println(cad.concat(" ").concat(cad2));
        
        /* CLASE CARACTERES */
        
        Character.isLetter(letra); // si es una letra devuelve verdadero , si no falso
        Character.isDigit(letra);  // si es un numero devuelve verdadero , si no falso
        Character.isSpaceChar(letra); //si es un espacio devuelve verdadero , si no falso
        Character.isUpperCase(letra); // si es mayuscula devuelve verdadero , si no falso
        Character.isLowerCase(letra); // si es minuscula devuelve verdadero , si no falso
        Character.toUpperCase(letra); // pasa el caracter a mayuscula
        Character.toLowerCase(letra); // pasa el caracter a minuscula
        Character.toString(letra);  // convierte el caracter en un String
        Character.getType(letra);  // no dice que categoria es el caracter.
        
        /* FORMAT
        * String nombre = "pepito";
        * int edad = 15;
        * String.format("Nombre:%s, edad:%d años", nombre, edad);
        * obtendriamos : Nombre: pepito, edad: 15 años.
        * 
        * formato del Format --> %[indice del argumento] [banderas] [tamaño] [.precision] tipo
        * 
        * % marca el inicio de cada uno de los argumentos
        * indice del argumento indica el orden en el que se usan las variables que va haber despues de la coma
        * Banderas : - para justificar a la izquierda, # incluye un radical de enteros y una coma para decimales, + incluye un signo +, " " espacio en los valores positivos, 0 se llegan los espacios con ceros en los valores positivos, , separador especifico de zona, ( encierra los numeros negativos en parentesis.
        * width indica el numero minimo de caracteres que tendrá la salida
        * .precision (.2) indica el numero maximo de digitos despues de la coma decimal
        *  tipo : b para boolean, c caracter unicode, d entero, f decimal, s cadena, t fecha y hora
        *
        * Ej: System.out.printf("cateto:%d > cateto:%d >> %.2f\n", 5,10, Math.hypot(5, 10));
        * 
        */
        
        
        /* STRINGBUILDER Y STRINGBUFFER */
        
        // inicializamos
        StringBuilder s1 = new StringBuilder(); // lo crea vacio con capacidad para 16 caracteres por defecto
        StringBuilder s2 = new StringBuilder(55); // lo crea con la capacidad que se le pase como argumento
        StringBuilder s3 = new StringBuilder("Hola"); // lo crea en base a la cadena que se le pasa.
        
        //Metodos
        s1.append("Hola"); //añade el argumento pasado al final, devuelve un StringBuilder
        s1.capacity(); // devuelve un entero con la capacidad
        s3.length(); // devuelve un entero con el numero de caracteres que tiene la cadena.
        s2.reverse(); // invierte el orden de los caracteres de la cadena.
        s3.setCharAt(3, '.'); // cambia el caracter indicado por el que le pasamos como argumento.
        s3.charAt(3); // nos devuelve el caracter que se encuentra en esa posición.
        s2.setLength(80); // cambia la capacidad del StringBuilder por el entero pasado como argumento.
        //importante
        cadena.toString(); // convierte una cadena en StringBuilder
        s3.delete(0, 3); // borra la cadena de caracteres comprendidad entre el primer argumento y el segundo
        s3.deleteCharAt(2); // borra el caracter en la posicion pasada como argumento
        s3.indexOf(cad); // analiza los caracteres de la cadena y devuelve la posicion del caracter si lo encuentra o -1 si no lo encuentra 
        s3.substring(2, 8); // devuelve la cadena comprendida desde el primer argumento pasado hasta el segundo.
        
        s3.insert(5, "adios"); //añade en la posicion indicada la cadena que se le pasa como argumento.
        
        /* OBJETOS
        * instanciar un objeto
        * NombreClase nombreObjeto = new NombreClase();
        * 
        * para poder instanciar un objeto necesitmos una clase con un constructor por defecto como minimo
        * CONSTRUCTOR POR DEFECTO 
        * NombreClase(){}
        * 
        * CONSTRUCTOR AL QUE SE LE PASAN PARAMETROS
        * NombreClase(int n, String s){ nombre = n; cadena = s;}
        * 
        * en la clase declaramos las variables que vamos a necesitar usar y en el constructor las inicializamos 
        * 
        * private final float IVA;
        * public int cantidad;
        * public double precioUnitario;
        * public double ImporteTotal;
        * 
        * NombreClase (){ this.IVA = 0.21; this.cantidad = 10; this.precioUnitario = 0.35; this.importeTotal  = (this.precioUnitario * this.cantidad) + ((this.precioUnitario * this.cantidad) * this.IVA ); }
        * 
        *
        * METODOS
        * utilizamos metodos para trabajar dentro de las clases , la estructura de un metodos puede ser normal o STATIC
        * normal tenemos que indicar si es public o privada luego el tipo que devuelve ( String, int , Otro Objeto , nada(void), un arraylist , etc ) y luego el nombre seguido de unos parentesis y los argumentos si fueran necesraios
        * public void actualizarImporteTotal(){ this.importeTotal = (this.precioUnitario * this.cantidad) + ((this.precioUnitario * this.cantidad) * this.IVA );}
        *
        *
        */
        
        /* FUNCIONES 
        * Son como los metodos pero estas estan en el main y se utilizan siempre indicado que son Static
        * public Static void EjecutarMenu(int n){ ----- }
        *
        */
        
        /* CLASES INTERESANES */
        /* 
        * CLASE MATH para las operaciones matematicas
        * Math.abs(numero) // convierte el numero pasado en valor absoluto
        * Math.pow(num, exponente) // calcula el numero elevado al exponente
        * (int) (Math.random() * 10) + 1 // enteros entre el 1 y el 10
        * 
        * CLASE LocalDate para las fechas
        * hay que importar java.time.*;
        * 
        * LocalDate (fecha sin hora)
        * LocalTime (Hora sin fecha)
        * LocalDateTime (combinacion de las dos anteriores)
        * 
        * LocalDate fec = LocalDate.now(); // guardamos en el objeto fec la fecha de hoy
        * LocalDate fec = LocalDate.of(AAAA,MM,DD); // pasamos la fecha en enteros separados por comas
        * LocalDate fec = LocalDate.parse ("AAAA,MM,DD"); // pasamos una cadena con la fecha
        * 
        * fec.getYear(); // sacamos el año de la fecha
        * fec.getMonth(); // sacamos el mes de la fecha
        * fec.DayOfWeek(); // sacamos el dia en ingles
        * fec.DayOfWeek().getValue(), // sacamos un numero de 1 a 7 de lunes a domingo
        * fec.toString(); // Obtenemos una cadena a partir de una fecha
        * fec.plus(cantidad, unidad); // sumamos x dias o x meses o x años a una fecha)      *la unidad es ChronoUnit.HOURS, ChronoUnit.MINUTES , ChronoUnit.DAYS, ChronoUnit.WEEKS, ChronoUnit.MONTHS, ChronoUnit.YEARS
        * fec.minus(cantidad, unidad); // restamos x dias o x meses o x años a una fecha)    * y hay que importar java.time.ChornoUnit;
        * 
        * fec.isBefore(fec2) fec.isAfter(fec2) fec.isEquals(fec2) // pasamos una fecha como parametro y obtenemos verdadero o false segun corresponda comparadnos si es antes, despues o igual las fehcas pasadas
        * 
        * PARA MAS INFO MIRAR CHULETA
        * 
        */
        
        /* ARRAYS Y ARRAYLIST
        * 
        * ARRAY 
        * 
        * Int[] numeros; String [] meses;
        * 
        * se declaran con el operador new y estableciendo una longitud que no podra variar 
        * int [] edad = new int[10]; 
        * String [] coches = {"Volvo", "BMW", "Ford", "Mazda"}
        * 
        * para imprimir un array necesitamos de un bucle for
        * 
        * for (int i = 0; i < array.length ; i++{ System.out.print(array[i]+ " ");}
        * 
        * resultado --> 1 2 6 8 5 2 6 85 41 52 
        * 
        * Se puede usar el bucle for each 
        *  
        * for (String c : coches)
        *   System.out.println(c);
        * esto significa para la cadena c del array coches imprime el valro de c
        * 
        * Busqueda, ordenacion y copia en arrays no voy a escribirla aqui.
        * 
        *  ARRAYS BIDIMENSIONALES 
        * 
        * se declaran asi 
        * int [][] arreglo = new int [30][3]; // esto significa que el array tendra 3 filas de 30 columnas cada fila
        * 
        * recorrer un array bidimensional se hace con un for doble
        * 
        * for ( int i = 0; i < arreglo.length ; i++
        *   for (int j = 0 ; j < arreglo[i].length; j++
        *       System.out.pirntln(arreglo[i][j])
        * 
        * ARRAYlIST
        * 
        * Se definen de esta manera 
        * ArrayList <Objeto> arreglo;
        * y en el contructor 
        * arreglo = new ArrayList<>();
        *
        * dento de los signos <> a la ora de definir hay que especificar el emboltorio. las posibilidades son
        * 
        * Boolean, Byte, Character, Integer, Float, Double, Long, Short
        * 
        * Asi pues un ArrayList de enteros se instanciaria de la siguietne manera
        * ArrayList <Integer> arreglo = new ArrayList <>();
        * 
        * Metodos del arrayList
        * 
        * arreglo.size() // nos dice la longitud
        * arreglo.add(x) // añadir un elemento 
        * arreglo.add(posicion, x) // añadir un elemento en una determinada posicion
        * arreglo.get(posicion) // nos devuelve un elemento que esta en la posicion que le pasamos
        * arreglo.remove(posicion) // elimina el elemento de una determinada posision, devuelve el elemento eliminado
        * arreglo.remove(x) // elimina la la primera ocurrencia del objeto x, devuelve true
        * arreglo.clear() // elimina todos los elementos
        * arreglo.set(posicion, x) // sustituye el el emento que se encuentra en la posicion indicada por el elemento que le pasamos
        * arreglo.contains(x) // comprueba si el elemento pasado se encuentra dentro del array
        * arreglo.indexOf(x) // devuelve la posicion de el elemento pasado, -1 si no lo encuentra
        * arreglo.Equals(list) // compara dos ArrayList completos devuelve true o false
        * Collections.sort(arreglo) // ordena los elementos del arraylist y para hacerlo en orden inverso Collections.reverseOrder(arreglo);
        * 
        * se puede imprimir con un simple 
        * System.out.println(arreglo);
        * 
        * y tambien podemos recorrelo con un for y con un for each como haciamos con los arrays normales
        * 
        * Para crear un alias de un arraylist (casi como copiar) --> ArrayList <Objeto> arreglo1 = arreglo // no copia si no que crea un alias
        * 
        * Para copiar --> ArrayList <Objeto> arreglo1 = new ArrayList <>(arreglo>;
        *
        * ArrayList Bidimensionales 
        * 
        * Se crean ArrayList<ArrayList<Objeto>> arreglo = new ArrayList<>();
        *  
        * para añadir un elemento la instruccion sera array.add(new ArrayList<>());
        * y para añadir valores a los elementos array.get(fila).add(valor); // para añadir un valor en la columna
        * y para coger array.get(fila).get(columna);
        *
        * para recorrerlo con un for se necesita el array.size() para las filas y array.get(fila).size() para las columnas
        *
        *
        * se recorre con un for doble 
        * for (int i = 0; i < array.size(); i++)
            System.out.printl("Fila: " +i+ " ." );
        *   for (int j = 0; j < array.get(i).size(); j++)
        *       System.out.printl(array.get(i).get(j)+" ");
        *
        */ 
         


```
