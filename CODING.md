# Components Starter

Modified version of the Stencil Component Starter - no one wants to see me rename things

* show component and test
* celcium first
* fahrenheit next

Finished code:

```TypeScript
import { Component, Prop } from '@stencil/core';

@Component({
  tag: 'kws-temperature',
  styleUrl: 'kws-temperature.css'
})
export class KwsTemperature {
  @Prop() scale: string;
  @Prop() temperature: number;

  render() {
    if (this.temperature || this.temperature === 0) {
      if (this.scale === 'C') {
        return <span>{(this.temperature - 273.15).toFixed(0)} ℃</span>;
      } else {
        return (
          <span>{((this.temperature * 9) / 5 - 459.67).toFixed(0)} ℉</span>
        );
      }
    }
  }
}
```

Next show the kws weather widgets project itself and walk through it a bit.

Be sure the note that this has been `npm link`'ed

*Note:* In all the following cases, need to `npm link kws-weather-widgets`

# Ionic Weather

The Ionic Weather application is an `@ionic/angular` application.

* CUSTOM_ELEMENTS_SCHEMA
* defineCustomElements
* use it...

# Angular Tents

* CUSTOM_ELEMENTS_SCHEMA
* defineCustomElements
* use it...

## `app.component` Files

```scss
kws-temperature { 
  font-size: 36px; 
  cursor: pointer; 
} 
```

```TypeScript
export class AppComponent { 
  title = 'app'; 
  scale = 'F'; 
  temperature = 297; 
} 
```

```HTML
<div> 
  <kws-temperature scale="{{scale}}" temperature="{{temperature}}" (click)="scale = scale === 'C' ? 'F':'C'"> 
  </kws-temperature> 
</div> 
```

# Vue Our Gear

## `main.js`

```JavaScript
import { defineCustomElements } from 'kws-weather-widgets';

Vue.config.productionTip = false;
Vue.config.ignoredElements = [/ion-\w*/];

defineCustomElements(window);
```

## `HelloWorld.vue`

```HTML
<div class="title">
  <img src="../assets/logo.png">
  <h1>{{ msg }}</h1>
  <div>
    <kws-temperature :scale="scale" :temperature="temperature" @click="scale = scale === 'C' ? 'F' : 'C'"></kws-temperature>
  </div>
</div>
```

```JavaScript
export default {
  name: 'HelloWorld',
  data() {
    return {
      scale: 'F',
      temperature: 300
    };
  },
  props: {
    msg: String
  }
};
```

```CSS
kws-temperature {
  font-size: 36px;
  cursor: pointer;
}
```

# Campsite React Shuns

## `index.js`

```JavaScript
import { defineCustomElements } from 'kws-weather-widgets';

ReactDOM.render(<App />, document.getElementById('root'));
registerServiceWorker();
defineCustomElements(window);
```

## `App.js`

```JavaScript
constructor(props) {
  super(props);
  this.state = {
    scale: 'F',
    temperature: 301
  };
}
```

```HTML
<div className="content">
  <div className="temperature">
    <kws-temperature
      temperature={this.state.temperature}
      scale={this.state.scale}
      onClick={() =>
        this.setState({
          scale: this.state.scale === 'C' ? 'F' : 'C',
          temperature: this.state.temperature
        })
      }
    />
  </div>
  ...
</div>
```

## `App.css`

```CSS
.temperature {
  font-size: 36px;
  text-align: center;
  cursor: pointer;
}
```