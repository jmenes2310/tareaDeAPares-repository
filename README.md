# Tarea de a Pares
- Valiente Octavio Joaquin :student:
- Menes Juan Manuel :student:
- Asignatura: Diseño de Sistemas 📚
- Enunciado: Dado el enunciado de final titulado "Cuidándonos", cuya fecha data el 27/02/2019, deberán resolver de a pares el punto de Modelado de Dominio (punto 1 y punto 2 de la sección Modelo de Dominio). Link: https://drive.google.com/file/d/1bZ8jy9CH_h2mJMvkfXYspqD48YF9Vasn/view?usp=sharing


#Justificaciones 📝🤓
En la relacion entre Persona y TipoDeUsuario decidimos usar un Patron State, ya que, se genera una abstraccion de cada tipo de usuario que puede ser una persona y además los estados se conocen entre sí, es decir, se puede pasar de un estado a otro. El comportamiento que tenga la persona dependerá del tipo de usuario que tenga en ese momento. Si es un usuario pasivo podrá aceptar ser el cuidador de un transeunte en un determinado viaje. Tambien un cuidador puede decidir comenzar un viaje y de este modo cambia su tipo de usuario a "transeunte". Una vez que el transeunte decide finalizar el viaje, volverá a estar con un tipo de usuario cuidador. 
Para realizar el calculo de distancias (implementando la api de Google en nuestro sistema) nos dirigimos a utilizar una patrón Adapter. Este nos permitía seguir adelante sin tenernos que preocupar de como calcularia la distancia, los único que necesitabamos saber es los datos que requería y usar una interfaz para que entienda el mensaje "calcularDistanciaEntre(origen, destino)". Esto tambien nos aportaría escalabilidad por si en un futuro decide cambiarse de api, por algún motivo. 
Para las formas de reaccionar a cierto evento decidimos inclinarnos por un patrón Satrategy. Decidimos este patrón porque cada forma de reaccionar implementa su propio algoritmo y su forma de llevar a cabo la tarea. Además nos posibilita en un futuro poder agregar mas formas de reaccionar sin interferir con el resto del sistema. 
Luego para los tipos de viaje decidimos usar una clase abstracta "Viaje" y que de ella hereden las clases "ViajeSimple" y "ViajeMultiple". Decidimos usar una herencia porque entre ellas hay comportamiento repetido. Pero, tienen distintas maneras de comunicar a sus cuidadores y calcular distancias o tiempos. Mientras que, en ViajeSimple solo se posee un destino y se notifica al cuidador a llegar, en ViajeMultiple se puede especificar detenerse N miuntos en cada parada o ir avisando destino a destino.
Entre la clase abtracta "ViajeMultiple", "NMinutosEnCadaParada", "EstadoSaludPuntoAPunto" decidimos implementar un Template Method. Porque, el viaje al iniciarse ejecuta una serie de pasos en un orden determinado, pero dependiendo si es una clase u otra hará cosas diferentes.


