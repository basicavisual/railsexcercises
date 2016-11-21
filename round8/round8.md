# Consigue que tu aplicación se vea en miaplicacion.dev

El propósito es (creo) entender cómo funcionarían los url's en producción, mientras se está desarrollando la aplicación.

Empiezo por descubrir que `cualquiercosa.dev` en el navegador, me lleva al index.html de apache que se encuentra en `var/www/html`. Esto es porque los dominios punto dev se utilizan para testing. El reto es, pues, lograr que al iniciar el servidor de rails pueda usar `cualquiercosa.dev` para entrar a la aplicación (cosa que no sucede, porque al iniciar el servidor de rails `cualquiercosa.dev` me lleva al archivo index.html de apache).

Una solución corta a esto es modificar el [hosts file](https://linux.die.net/man/5/hosts) para que la entrada sea la siguiente:

```
127.0.0.1  miaplicacion.dev   localhost
```

La solución larga (pero más eficiente) es utilizar un proxy como [Prax.cr](https://github.com/ysbaddaden/prax.cr), pero eso lo veremos después. Es larga porque requiere el uso y configuración de otra aplicación, es más eficiente porque con el método hosts debes definir el url para cada entrada en el archivo hosts.
