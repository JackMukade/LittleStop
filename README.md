# Primer proyecto con ReactJs

# ¿Qué es reactjs?
Es un proyecto sencillo donde se aprendieron los conceptos de reactjs

# ¿Para que sirve?
ReactJs es una libreria open source en donde se pueden hacer aplicaciones de una sola pagina, 
se puede usar para controlar la vista para aplicaciones web y moviles.

# Ventajas de React
Mejora el desempeño con el Virtual DOM, JSX es mas facil de leer y escribir, diseño atomico.

# Desventajas de React


# JSX
JSX puede recordarte a un lenguaje de plantillas, pero viene con todo el poder de JavaScript. 

# Elemento
Es un pequeño bloque plano, “constituyen” los componentes y son inmutables
Ejemplo: 
const element = (
    <div>
        <h1>Hello, world!</h1>
        <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
);

# Componentes
Los componentes son formados por los elementos y son como las funciones de JS y aceptan
entradas de props, se pueden hacer de dos maneras.

Funciones
function ProfilePage(props) {
  
  const handleClick = () => { setTimeout(showMessage, 3000); };

  return ( < button onClick={handleClick}>Seguir</ button > );

}

Clases
function ProfilePage(props) {
 
  const handleClick = () => { setTimeout(showMessage, 3000); };

  return (< button onClick={handleClick}>Seguir</ button>);

}

La principal diferencia seria que antes las clases daban mas funcionalidades como las de state
pero ahora con los hooks useState, useContext por ejemplo ya es posible usar las funciones con mas frencuencia

en este proyecto solo se usaron componentes con funciones

# Como usar los metodos o event handlers in JSX callbacks

Forma 1 Binding in Constructor (Larga)
class Component extends React.Component {

  constructor(props) {
    super(props);
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() { } 
}


Forma 2 Public class fields syntax (La uso aqui)
handleClick = () => { console.log('this is:', this); };

<button onClick={this.handleClick}>{'Click me'}</button>

Forma 3 Arrow functions in callbacks (No muy recomendable si usas props)
<button onClick={(event) => this.handleClick(event)}>{'Click me'}</button>
Note: If the callback is passed as prop to child components, those components might do an extra re-rendering.

# Como pasar datos a un event handler o callback
Forma 1
<button onClick={() => this.handleClick(id)} />

Forma 2
<button onClick={this.handleClick.bind(this, id)} />


# Que es una callback
Es una funcion que recibe otra funcion
Ejemplo
button.addEventListener('click', showAlert); la funcion addEventListener dice cuando ejecutar el callback

# Para que sirve la prop Key
Se usa cuando se hacen elementos en array y ayuda a react a saber que elementos son modificados

# Para que sirve context
Contexto da una manera de pasar datos sin pasar por todo el arbol de componentes de manera manual

# Por que se usa className
Por que class es una palabra clave de js y jsx es una extension de js 

# Fragments vs Container Divs
Es un patron que es usado para regresar multiples elementos, permite agrupar varios hijos sin hacer extra nodos 
<> Hijos </>
Fragments son mas rapidos y ocupan menos memoria y no interrumpe el Flexbox y Grid 

# Componentes sin estado
En todo el proyecto se usan estos componentes sin estado, son facil de escribir, entender, rapidos y no es necesario usario el this.
Nota: en versiones 16.8 es posible trabajar asi con los componentes sin estado usando sus HOOKS

import React, {useState} from 'react';

const App = (props) => {
  const [count, setCount] = useState(0);
  return ()
}

# Componentes con estado
Se usan cuando quieres quieres manejar el ciclo de vida  y los estados por ejemplo
class App extends Component {

  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() { }

}


# Decoradores
Con estos puedes pasar varios valores a una función

const setTitle = (title) => (WrappedComponent) => {

  return class extends React.Component {
    componentDidMount() { document.title = title; }
    render() { return <WrappedComponent {...this.props} />; }
  };

};


# Material UI y Styled Components
Son usados en este sistema para ver su funcionamiento.

# React Router 
Tambien es usado en este pagina para probar la navegación.

# Firebase 
Utilizado el login para hacer pruebas.