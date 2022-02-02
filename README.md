
<div style="text-align: center;">
  <h2>Configuración commitizen en español</div>
  <div style="text-align: center;">
    <img src="https://img.shields.io/badge/Build-NodeJS-%233c873a.svg??style=flat"/>
    <img src="https://img.shields.io/badge/Install-NPM-%23c23535.svg??style=flat"/>
    <img src="https://img.shields.io/badge/Install-YARN-%232c8ebb.svg??style=flat"/>
  </div>
</p>

cz-configuracion-es es un paquete de configuración para commitizen basado en cz-emoji que traduce y ofrece un par de mejoras al template.

![2022-02-02 13-39-43](https://user-images.githubusercontent.com/61033998/152226684-544fccea-e335-479d-8338-bec57f6b3ecf.gif)

### 🔧 Instalación de dependencias

Instalar yarn con el siguiente comando:
```sh
$ npm install --global yarn
```

### 📦 Instalación

Usando **npm**:
```sh
$ npm install --save-dev <DireccionDeDescargaDelPaquete>
```
Usando **yarn**:

```sh
$ yarn install --dev <DireccionDeDescargaDelPaquete>
```

Agregar a `package.json`:
```json
"config": {
  "commitizen": {
    "path": "./node_modules/cz-configuracion-es"
  }
}
```
Alternativamente se puede agregar un archivo `.czrc` y se agregaría de la siguiente forma: 
```json
{
  "path": "./node_modules/cz-configuracion-es"
}
```
<p style="font-size:0.9rem; font-weight:bold;">Nota: Esta es la manera recomendada para agregar la configuración.</p>

### Uso del template
Para visualizar el template escribimos el siguiente comando en la consola:
```sh
git cz
```
### Personalización
La configuración de `cz-configuracion-es` puede manejarse desde un archivo `.czrc` o desde `package.json`, se agrega de la siguiente forma:

```json
{
  "config": {
    "cz-configuracion-es": {}
  }
}
```

#### Opciones de configuración

##### ✨ Types:
Por defecto se tenemos 11 types que se puede utilizar en nuestra configuración, para poder agregar una lista de types personalizada se deberá de agregar un nodo `types` a la configuración cada elemento dentro de `types` esta será un objeto con los nodos `emoji`, `code`, `description` y `name` de la siguiente manera:
```json
{
  "config": {
    "cz-configuracion-es": {
      "types": [
        {
          "emoji": "🧪",
          "code": ":test_tube:",
          "description": "Creación de pruebas o correcciones a las existentes.",
          "name": "test"
        }
      ]
    }
  }
}
```
##### ✨ Scopes:
Se puede proporcionar dentro de la configuración una lista de scopes posibles para elegir cuando se construye el commit, si esta variable no se encuentra entonces se le pedirá al usuario que ingrese de forma manual el scope del commit.
```json
{
  "config": {
    "cz-configuracion-es": {
      "scopes": ["style", "feat", "ci"]
    }
  }
}
``` 
##### ✨ Symbol
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
##### ✨ Saltar preguntas
Dentro de la configuración se puede proporcionar un arreglo con las preguntas que no se necesita que se pregunten mientras se construye el commit, solo es posible saltarle preguntas opocionales
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

##### ✨ Preguntas personalizadas
Un objeto que contiene los textos que sobre escribirán los textos por defecto
Debe tener un nodo con el nombre la pregunta a la que se desea cambiar el texto.

<p style="font-weight:bold; font-size:0.9rem">Nodos posibles:</p>

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
##### ✨ Personalización de maximo de caracteres en subject

La cantidad máxima de caracteres disponibles en el subject. (Recordatorio: El máximo según las reglas de commits convencionales debería de ser 75)

```json
{
  "config": {
    "cz-configuracion-es": {
      "subjectMaxLength": 200,
    }
  }
}
```
### License

MIT Copyright © 2022 Mauricio Miramontes Ramírez and Carina Jiménez García.

### Colaboradores

<a href="https://github.com/CariJG"><img style="width: 60px;height: 60px;" src="https://user-images.githubusercontent.com/64931832/152250524-3f4fdde3-2f4e-4de3-90bf-1663df9f66a0.png"/><a/>
<a href="https://github.com/MauricioMiramontes"><img style="width: 60px;height: 60px;" src="https://user-images.githubusercontent.com/64931832/152250482-00401807-8b38-4664-a3af-a4b9a31ed6bd.png"/><a/>
