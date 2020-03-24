# solar-jump-vue

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


# Running

First run solar-jump. The repository is located here: 
https://github.com/ARedfearn/solar-jump

Add some planets using:

```
$ curl -i -H 'Content-Type:  application/json' -d '{"name" : "jupiter","gravity" : 24.79}' -X PUT  http://localhost:8086/planet
```

planets
```
 Planet	Gravity m/s²
    Earth 9.81
    Moon 3.03
    Mercury	3.7
    Jupiter	24.97
    Mars	3.71
    Saturn	10.44
    Uranus	8.87
    Neptune	11.15
``` 

Run locally using

```
npm run serve 
```

Jump to your hearts content
