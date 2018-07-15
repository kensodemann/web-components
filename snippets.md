# Vue HTML && HTML


```JSON
  "Scale Change on Click": {
    "prefix": "kws-click",
    "body": "scale = scale === 'C' ? 'F' : 'C'"
  }
```

# TypeScript React


```JSON
  "Kelvin to Celcius":{
    "prefix": "kws-celcius",
    "body": "{(this.temperature - 273.15).toFixed(0)}"
  },
  "Kelvin to Fahrenheit":{
    "prefix": "kws-fahrenheit",
    "body": "{((this.temperature * 9) / 5 - 459.67).toFixed(0)}"
  },
  "Scale Property":{
    "prefix": "kws-scale",
    "body": "@Prop() scale: string;"
  },
  "Temperature Property":{
    "prefix": "kws-temp",
    "body": "@Prop() temperature: number;"
  }

```

# JavaScript 


```JSON
  "React Constructor": {
    "prefix": "kws-constructor",
    "body": [
      "constructor(props) {",
      "  super(props);",
      "  this.state = {",
      "    temperature: 305,",
      "    scale: 'F'",
      "  };",
      "}"
    ]
  },
  "React Render": {
    "prefix": "kws-render",
    "body": [
      "<div className=\"temperature\">",
      "  <kws-temperature",
      "    temperature={this.state.temperature}",
      "    scale={this.state.scale}",
      "    onClick={",
      "      () => this.setState({",
      "        temperature: this.state.temperature,",
      "        scale:this.state.scale === 'C'?'F':'C'",
      "      })",
      "    }",
      "  />",
      "</div>"
    ]
  }
```

# CSS and SCSS


```
  "Style the Temperature": {
    "prefix": "kws-css",

    "body": [
      "kws-temperature {",
      "  font-size: 36px;",
      "  cursor: pointer;",
      "}"
    ]
  }
```
