# Integrantes

- Luz Diana Deniz Irala
- Lucas Nicolas Chiesa Sturla

# Aclaracion de archivos

En el archivo ```class_diagram``` se encuentra el primer diagrama de clases previo a la implementacion de paradas en el dominio del problema. Mientras que en el archivo ```class_diagram_v2``` se encuentra el segundo diagrama de clases con la implementacion de paradas y estrategias para saber que va a hacer en cada parada.

Por otro lado escribimos el pseudocodigo que corresponde al calculo de demoras en el archivo ```pseudocodigo.md```

# Explicacion

Utilizamos el patron de diseño Strategy en dos lugares:

- IncidentStrategy: Esta estrategia se encarga de actuar de una forma u otra en caso de un incidente segun lo que tenga definido en cada clase especifica.

Tenemos definidas 4 estrategias: 

    - SendNotificationToCareTarkers: Esta estrategia enviara una notificacion a los cuidadores.
    - CallPolice: Llama a la policia.
    - CallActiveUser: Llama al celular del usuario.
    - WaitXMinutes: Espera "X" minutos para ver si es falsa alarma.

- StopStrategy: Esta estrategia calcula la demora aproximada segun la estrategia que haya tomado en el viaje para que hacer en cada parada.

Ademas algo que nos gustaria recalcar es que usamos herencia en el caso de los usuarios ya que consideramos que un usuario podia ser activo y pasivo al mismo tiempo. Entonces lo que terminamos definiendo es que exista una clase User que tenga los comportamientos de un usuario pasivo y un ActiveUser el cual le agrega el comportamiento de un usuario activo.