Tutorial
--------

Cada función en Python recibe un númeropredefinido de argumentos,si se declaran normalmente,de la siguiente manera:

    def mifuncion(primero, segundo, tercero):
        # Hacer algo con las 3 variables
        ...

Es posible declarar funciones que reciban un número variable de argumentos,usando la siguiente sintaxis:

    def foo(primero, segundo, tercero, *therest):
        print "Primero: %s" % primero
        print "Segundo: %s" % segundo
        print "Tercero: %s" % tercero
        print "Y el resto de argumentos... %s" % list(therest)

La variable "therest" es una lista de argumentos,La cual recibe todos los argumentos que fueron dados a la función "foo" después de los 3 primeros argumentos. Entonces,llamando a la función foo(1,2,3,4,5) imprimiría:
 
    Primero: 1
    Segundo: 2
    Tercero: 3
    Y el resto de argumentos...... [4, 5]

También es posible enviar argumentos con palabras clave, para que así de esta forma no importe el orden de los argumentos, utilizando la siguiente sintaxis:

    def bar(primero,segundo,tercero, **options):
        if options.get("accion") == "sumar":
            print "La suma es: %d" % (primero+segundo+tercero)

        if options.get("numero") == "primero":
            return primero

    resultado = bar(1, 2, 3, accion = "sumar", numero = "primero")
    print "Resultado: %d" % resultado

El siguiente código da el siguiente resultado:

    La suma es: 6
    Resultado: 1

La función "bar" recibe 3 argumentos.Si un argumento adicional "accion" es recibido y su instrucción es sumar los números, entonces la suma se imprimer.Alternativamente,la función también sabe que debe retornar el primer argumento siel argumento "numero" tiene como instrucción primero.

Ejercicio
--------


Completa las funciones ´foo´ y ´bar´ para que ambas puedan recibir una cantidad variable de argumentos(3 o más)
La función ´foo´ debe retornar la cantidad extra de argumentos recibidos.
La función  ´bar´deber retornar ´True´ si el argumento con la palabra clabe ´magicnumber´ es 7, sino retornará ´False´.

Código de tutorial
-------------

# Edita las funciones prototipo e implementación
def foo(a, b, c):
    pass

def bar(a, b, c):
    pass


# test code
if foo(1,2,3,4) == 1:
    print "Bien."
if foo(1,2,3,4,5) == 2:
    print "Mejor."
if bar(1,2,3,magicnumber = 6) == False:
    print "Excelente."
if bar(1,2,3,magicnumber = 7) == True:
    print "Increible!"

Salida esperada
---------------
Bien.
Mejor.
Excelente.
Increible!

Solución
--------
# edita las funciones prototipo e implementación
def foo(a, b, c, *args):
    return len(args)

def bar(a, b, c, **kwargs):
    return kwargs["magicnumber"] == 7


# test code
if foo(1,2,3,4) == 1:
    print "Good."
if foo(1,2,3,4,5) == 2:
    print "Better."
if bar(1,2,3,magicnumber = 6) == False:
    print "Great."
if bar(1,2,3,magicnumber = 7) == True:
    print "Awesome!"
