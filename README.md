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

* Se deberia tener por separado el codigo html y la logica.
* Se podria crear una funcion como "TemplateHTML()" el cual contenga el HTML de la web cpns etiquetas y esta funcion tenga tenga como parametros las propiedas del control HTML a dibujar. Ejm:

```html
const TemplateHTML = (prop) => [
    <h1 key="name">{`Nombre: ${prop.name}`}</h1>,
    <h2 key="location">{`País: ${prop.location}`}</h2>
];
```
 


