# PruebaSoaIntFrontEnd - Desarrollo Front End:

```html
class FetchGithub extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: '',
      location: ''
    };
  
​
  componentDidMount() {
    fetch('https://api.github.com/users/workshopsjsmvd')
      .then(res => {
        this.setState({
          name: res.name,
          location: res.location
        })
      });
  }
​
  render() {
    return [
      <h1 key="name">{`Nombre: ${this.state.name}`}</h1>,
      <h2 key="location">{`País: ${this.state.local}`}</h2>
    ];
  }
}
​
ReactDOM.render(
  <FetchGithub />,
  document.getElementById('root')
);


```

## Analisis del codigo en ReactJs:

* La propiedad "this.state.local" no existe, deberia cambiarse por "this.state.location", esto ocasionaria un error:

```html
   <h2 key="location">{`País: ${this.state.local}`}</h2>
```

* Se deberia tener por separado el codigo html (etiquetas hmtl) y la logica (codificacion) para poder serguir unas buenas practicas

* Se podria crear una funcion como "TemplateHTML()" el cual contenga el HTML de la web con las etiquetas y esta funcion tenga como parametros las propiedas del control HTML a dibujar. 
* Por Ejm se crea la funcion "TemplateHTML()":

```html
const TemplateHTML = (prop) => [
    <h1 key="name">{`Nombre: ${prop.name}`}</h1>,
    <h2 key="location">{`País: ${prop.location}`}</h2>
];
```

* A su vez esta funcion "TemplateHTML()" se llamaria en el "render()" de la siguiente manera:

```html
  render() {
    return (
      <TemplateHTML name={this.state.name}   location={this.state.location} 
      />
    );
  }
```
