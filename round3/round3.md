# Sirviendo un json
### _Servir un json file en el homepage_

La misión de este round es servir un json file en el homepage que dijera `{ "hello" = "world"}`.

Este reto resultó especialmente difícil porque tiene varias respuestas.

La respuesta que @mroutis esperaba era la siguiente, desde el controlador:

```
def show
  render json: { hello: "world" }
end
```
Nunca se me ocurrió que podía renderear directamente como si de una consola se tratara. Pensé que podría renderear contenido que tuviera como si fueran datos. Un tipo de dato `Hola`con un dato `mundo`(aunque me pareció una respuesta complicada para un problema simple) pero nevertheless experimenté rendereando datos hacia JSON y me encontré con que podía crear un api:

```
def show
    @article = Article.find(params[:id])
    render json: @article
end
```

Esto crea un json de los datos en la BD. Como dije, es overkill para la pregunta inicial. Pero me hice ver que rails tiene la función (¿se llama función?) para renderear datos a json.

Ahora sobre el overkill, en mi cabeza lo que me estaban pidiendo era renderear un archivo json. Así que eso hice. Construí un archivo json e intenté renderearlo usando el método render file: con el sigiuiente código:

```
def show
  render file: "usuario/nombredelapp/app/views/nombredelcontroller/archivo.json", content_type "application/json"
end
```

Me dio error de Missing template. Rails renderea a un HTML por default. Si tengo una clase, un recurso en mi routes file y un html.erb en mis vistas con el mismo nombre eso es lo que me va a renderear. (Ver [layouts and rendering](http://guides.rubyonrails.org/layouts_and_rendering.html)). El primer error fue poner el archivo en el mismo folder que el controlador. Rails y su "magia" asume que este es el render por defualt y falla porque no es un html.erb (o algo así) así que lo moví de carpeta y salió bien, pero me lo rendereó como html. Lo que hice fue quitarle el `content_type "application/json"` y listo.
