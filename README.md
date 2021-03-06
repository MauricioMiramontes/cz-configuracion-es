
<div style="text-align: center;">
  <h2>Configuraci贸n commitizen en espa帽ol</div>
  <div style="text-align: center;">
    <img src="https://img.shields.io/badge/Build-NodeJS-%233c873a.svg??style=flat"/>
    <img src="https://img.shields.io/badge/Install-NPM-%23c23535.svg??style=flat"/>
    <img src="https://img.shields.io/badge/Install-YARN-%232c8ebb.svg??style=flat"/>
  </div>
</p>

cz-configuracion-es es un paquete de configuraci贸n para [commitizen](https://github.com/commitizen/cz-cli), para poder utilizar esta configuraci贸n es necesario tener intalado y configurado commitizen de forma global, basado en [cz-emoji](https://github.com/ngryman/cz-emoji) que traduce y ofrece un par de mejoras al template.

![2022-02-02 13-39-43](https://user-images.githubusercontent.com/61033998/152226684-544fccea-e335-479d-8338-bec57f6b3ecf.gif)

### 馃敡 Instalaci贸n de dependencias

Instalar yarn con el siguiente comando:
```sh
$ npm install --global yarn
```

### 馃摝 Instalaci贸n

Usando **npm**:
```sh
$ npm install --save-dev <DireccionDeDescargaDelPaquete>
```
Usando **yarn**:

```sh
$ yarn install --dev <DireccionDeDescargaDelPaquete>
```

Agregamos a nuestro archivo `package.json`, la siguiente nodo `"config"` para indicarle a commitizen que acceda a nuestra configuraci贸n por defecto:
```json
"config": {
  "commitizen": {
    "path": "./node_modules/cz-configuracion-es"
  }
}
```
Si se desea tener la configuraci贸n de commitizen por separado, se recomienda crear un archivo llamado `.czrc` en la carpeta ra铆z, de la siguiente forma:

- package.json:
```json
"config": "./.czrc"`
```
- .czrc
```json
{
  "path": "./node_modules/cz-configuracion-es"
}
```
### Uso del template
Para visualizar el template escribimos el siguiente comando en la consola:
```sh
git cz
```

<p style="font-size:0.9rem; font-weight:bold;">Nota: Este comando funciona al momento de tener instalado commitizen de forma global.</p>

### Personalizaci贸n
Te ofrecemos diferentes formas de configurar el paquete `cz-configuracion-es`, con la finalidad de personalizar de acuerdo a tus requerimientos, esta configuraci贸n puede manejarse desde un archivo `.czrc` o desde `package.json`, se agrega de la siguiente forma:

```json
{
  "config": {
    "cz-configuracion-es": {}
  }
}
```

#### Opciones de configuraci贸n

##### 鉁? Types:
Por defecto se tenemos 11 types que se puede utilizar en nuestra configuraci贸n, para poder agregar una lista de types personalizada se deber谩 de agregar un nodo `types` a la configuraci贸n cada elemento dentro de `types` esta ser谩 un objeto con los nodos `emoji`, `code`, `description` y `name` de la siguiente manera:
```json
{
  "config": {
    "cz-configuracion-es": {
      "types": [
        {
          "emoji": "馃И",
          "code": ":test_tube:",
          "description": "Creaci贸n de pruebas o correcciones a las existentes.",
          "name": "test"
        }
      ]
    }
  }
}
```
<p style="font-size:0.9rem; font-weight:bold;">Nota: Al agregar el nodo types se sobrescribe todos los nodos types que se tienen por defecto.</p>

##### 鉁? Scopes:
Se puede proporcionar dentro de la configuraci贸n una lista de scopes posibles para elegir cuando se construye el commit, si esta variable no se encuentra entonces se le pedir谩 al usuario que ingrese de forma manual el scope del commit.
```json
{
  "config": {
    "cz-configuracion-es": {
      "scopes": ["style", "feat", "ci"]
    }
  }
}
``` 
##### 鉁? Symbol
Un valor booleano que permite utilizar el valor de UNICODE para los emojis en lugar del markup en un commit, por defecto symbol es `true`.
```json
{
  "config": {
    "cz-configuracion-es": {
      "symbol": false
    }
  }
}
```
##### 鉁? Saltar preguntas
Dentro de la configuraci贸n se puede proporcionar un arreglo con las preguntas que no se necesita que se pregunten mientras se construye el commit, solo es posible saltarle preguntas opocionales
- Preguntas obligatorias: `type`, `subject`.
- Preguntas opcionales: `scope`, `body`, `breaking`, `issues` y `coauthored`.
```json
{
  "config": {
    "cz-configuracion-es": {
      "skipQuestions": ["scope", "issues", "coauthored"]
    }
  }
}
```

##### 鉁? Preguntas personalizadas
En las configuraciones personalizadas exite el nodo `questios`, el cual hace referencia al texto de las preguntas, a continuaci贸n se enlistan los nodos que pueden cambiar.

<p style="font-weight:bold; font-size:0.9rem">Nodos:</p>

- `types`
- `scope`
- `subject`
- `body`
- `breaking`
- `coauthored`
- `issues`


```json
{
  "config": {
    "cz-configuracion-es": {
      "questions": {
        "body": "Mensaje personalizado del body",
        "coauthored" : "Mensaje personalizado del co-autor"
      }
    }
  }
}
```
##### 鉁? Personalizaci贸n de maximo de caracteres en subject

La cantidad m谩xima de caracteres disponibles en el `subject`.

```json
{
  "config": {
    "cz-configuracion-es": {
      "subjectMaxLength": 200,
    }
  }
}
```
<p style="font-size:0.9rem; font-weight:bold;">Nota: El m谩ximo seg煤n las reglas de commits convencionales deber铆a de ser 75.</p>

### License

MIT Copyright 漏 2022 Mauricio Miramontes Ram铆rez and Carina Jim茅nez Garc铆a.

### Colaboradores

<a href="https://github.com/CariJG"><img style="width: 60px;height: 60px;" src="https://user-images.githubusercontent.com/64931832/152250524-3f4fdde3-2f4e-4de3-90bf-1663df9f66a0.png"/><a/>
<a href="https://github.com/MauricioMiramontes"><img style="width: 60px;height: 60px;" src="https://user-images.githubusercontent.com/64931832/152250482-00401807-8b38-4664-a3af-a4b9a31ed6bd.png"/><a/>
