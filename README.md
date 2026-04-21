# trabajo.po
PARTE 1: Análisis Teórico y Reflexión

1. Rastro de mensajes desde el main

Todo empieza desde el objeto administración, que es el que coordina el proceso. Desde ahí se llama a un método como imprimirPropietarios(), que básicamente se encarga de mostrar la información.

Pero este objeto no hace todo por sí solo. Lo que hace es comunicarse con cada objeto Propietario y pedirle sus datos. Luego, cada propietario hace lo mismo con su Propiedad, y esta, si es necesario, le solicita información al CuartoUtil.

En resumen, el recorrido de mensajes sería algo así:
Main → Administracion → Propietario → Propiedad → CuartoUtil.

⸻

2. Navegación y Gestión de Memoria

Para pasar de un Propietario a su Propiedad, se utiliza un método como getPropiedad(), que devuelve un apuntador (Propiedad*). Por eso se usa el operador -> para acceder a sus métodos.

También se pueden encadenar llamadas. Por ejemplo, si se quiere saber si el cuarto útil está terminado, se puede hacer algo como:
propietario->getPropiedad()->getCuartoUtil()->isEstaTerminado().

Por otro lado, el tema de los destructores es clave. Como se está usando memoria dinámica con new, es necesario liberar esa memoria con delete. Si no se hace, el programa deja espacios ocupados en memoria incluso después de terminar, lo que se conoce como memory leak.
