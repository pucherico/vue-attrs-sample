<template>
  <div id="app">
    <h1>$attrs Sample</h1>
    <p>
      Esto es un ejemplo que demuestra las posibles formas de transmitir información desde un componente padre a componentes hijos:
    </p>
    <ul>
      <li>Mediante el uso de <em>props</em> (la forma natural entre componentes)</li>
      <li>Usando atributos (que no son definidos como <em>props</em>)</li>
      <ul>
        <li>El hijo hereda la información implícitamente (inheritAttrs)</li>
        <li>Haciendo uso de $attrs</li>
      </ul>
    </ul>
    <br>
    <div id="result">
      <HijoProp color="red" mensaje="Establecido color en el hijo usando propiedad" />
      <HijoAtr :style="{ backgroundColor: 'pink' }" mensaje="Establecido color en el padre" />
      <HijoAtrCustom color="lightblue" mensaje="Establecido color en el hijo con atributo del padre" />
      <!-- <div class="local">Hola, este cuadro está en el padre</div> -->
    </div>
    <ol>
      <li>En el primer cuadro, el hijo define una propiedad <em>color</em> y el padre establece el valor en la propiedad: <em>red</em>.</li>
      <li>
        En el segundo cuadro, el hijo no define ninguna propiedad, aún así, el padre puede establecer en el hijo el color usando el atributo de estilo sobre el componente.
        Nótese que el hijo hereda por defecto todos los atributos. Cambiar en el Hijo este comportamiento usando <em>inheritAttrs: false</em> y comprobar que el hijo ya no tiene el color
        asignado en el padre.
      </li>
      <li>
        En el tercer caso, el hijo no hereda los atributos definidos por el padre (<em>inheritAttrs: false</em>).
        Esto significa que los atributos no serán <em>renderizados</em>, sin embargo, el componente hijo 
        todavía puede acceder a esta información mediante <em>$attrs</em> y usar la información desde el componente hijo.
      </li>
    </ol>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import HijoProp from './components/HijoProp'
import HijoAtr from './components/HijoAtr'
import HijoAtrCustom from './components/HijoAtrCustom'

export default {
  name: 'App',
  components: {
    // HelloWorld
    HijoProp, HijoAtr, HijoAtrCustom
  }
}
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 60px;
}
#result {
  display: flex;
  background-color: wheat;
  justify-content: space-around;
  /* padding: 1em; */
}
#result > div {
  border: cornflowerblue solid 2px;
  border-radius: 8px;
  padding: 3em;
  margin: 1em;
}

.local {
  background-color: lightgreen;
}
</style>
