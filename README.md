# Análisis de My Reactive Farm

## Propósito del proyecto

El proyecto **My Reactive Farm** tiene como objetivo desarrollar una aplicación web interactiva utilizando **React y Vite**, que permita gestionar información relacionada con animales mediante el consumo de una API externa. La aplicación aplica conceptos fundamentales de React como componentes, manejo de estado, efectos, consumo de APIs y formularios, además de una correcta organización del proyecto y el uso de estilos modernos.

---

## Estructura del proyecto

El proyecto sigue una estructura típica de una Single Page Application (SPA) con React:

* **Raíz del proyecto**:

  * `.env`: contiene la configuración de la API.
  * `package.json` y `package-lock.json`: gestión de dependencias.
  * `vite.config.js`: configuración de Vite.
  * `eslint.config.js`: reglas de linting.
  * `folder-structure.txt`: descripción de la organización del proyecto.
  * `index.html`: punto de entrada de la aplicación.

* **Carpeta `src/`**:

  * `components/`: componentes reutilizables de la aplicación.
  * `hooks/`: contiene el archivo `useFetchAnimals.js`, preparado para lógica personalizada.
  * `pages/`: incluye `Farm.jsx`, que funciona como la página principal de la aplicación.
  * `services/`: contiene `animalApi.js`, encargado del consumo de la API.
  * `App.jsx`, `main.jsx`, `App.css` e `index.css`: inicialización y renderizado de la aplicación.

---

## Manejo del estado (`useState`)

El hook `useState` se utiliza para manejar el estado de la aplicación, principalmente en:

* El control de los filtros.
* El almacenamiento de los datos obtenidos desde la API.
* El manejo de errores y estados internos.

Esto permite que la interfaz se actualice de forma dinámica según las acciones del usuario.

---

## Uso de efectos (`useEffect`)

El hook `useEffect` se emplea para manejar efectos secundarios, como:

* La carga inicial de datos desde la API.
* La ejecución de lógica cuando el estado cambia.
* La interacción con servicios externos.

De esta forma, la aplicación responde correctamente al ciclo de vida de los componentes.

---

## Consumo de API con Axios y MockAPI

La aplicación consume una API creada en **MockAPI** para obtener y manipular datos relacionados con animales.

El consumo de la API se realiza mediante **Axios**, implementado en el archivo `animalApi.js`, donde se manejan operaciones como:

* `GET` para obtener datos.
* `UPDATE` para actualizar registros.
* `DELETE` para eliminar información.

Esto permite mantener separada la lógica de negocio del resto de la aplicación.

---

## Manejo de formularios y validaciones

El manejo de formularios se realiza en el componente `AnimalForm.jsx`. Este formulario incluye validaciones básicas que evitan el envío de información incompleta o incorrecta, garantizando datos válidos antes de enviarlos a la API.

Además, se controla el envío de datos y la limpieza de los campos del formulario.

---

## Uso de Tailwind CSS

El proyecto utiliza **Tailwind CSS** como framework de estilos. Está configurado de forma global y se usa a lo largo de toda la aplicación para:

* Diseñar la interfaz de usuario.
* Aplicar estilos responsivos.
* Mantener consistencia visual y facilitar el desarrollo.

---

# Cuestionario

## 1. ¿Cuál es la diferencia entre un componente presentacional y un componente de página en React?

Un **componente presentacional** se encarga únicamente de mostrar información en la interfaz. No maneja lógica compleja ni estados propios, solo recibe datos por props. En el proyecto, ejemplos de esto son `AnimalCard.jsx`, `Alert.jsx` y `Loader.jsx`.

Un **componente de página** representa una vista completa y contiene la lógica principal de la aplicación, como estados, efectos y peticiones a la API. En este proyecto, `Farm.jsx` cumple ese rol.

---

## 2. ¿Para qué se utiliza useState en el proyecto? Menciona dos estados distintos y su función.

`useState` se utiliza para manejar datos que cambian con la interacción del usuario.  
En el proyecto se usa, por ejemplo, para:

- Guardar los valores del formulario mientras el usuario escribe.
- Manejar filtros o selecciones que determinan qué animales se muestran.

---

## 3. ¿Cómo se usa useEffect para cargar datos desde MockAPI al inicio? Explica el flujo.

`useEffect` se usa para ejecutar la carga de datos cuando el componente se monta.  
Dentro del efecto se hace la llamada a la API, se activan los estados de carga, se guardan los datos obtenidos y se manejan posibles errores.

---

## 4. ¿Cómo maneja el proyecto los estados de loading, error y lista vacía? ¿Qué se muestra al usuario en cada caso?

- **Loading**: se muestra un spinner usando el componente `Loader`.
- **Error**: se muestra un mensaje de error con el componente `Alert`.
- **Lista vacía**: se muestra un mensaje indicando que no hay animales registrados.

---

## 5. ¿Qué significa que un formulario sea controlado en React? Relaciónalo con el formulario del proyecto.

Un formulario controlado significa que los valores de los inputs son manejados por el estado de React y no directamente por el DOM.  
En el proyecto, cada campo del formulario tiene un `value` y un `onChange` que actualiza el estado, lo que permite validar los datos y mostrar mensajes de error.

---

## 6. ¿Por qué es buena práctica separar la lógica de datos en archivos como animalsApi.js en vez de hacer peticiones dentro de los componentes?

Porque evita duplicar código, mantiene los componentes más limpios y facilita el mantenimiento. Además, las funciones de la API pueden reutilizarse en diferentes componentes sin repetir las peticiones.

---

## 7. ¿Qué hace que AnimalCard sea un componente reutilizable? ¿Cómo se podría usar una tarjeta similar en otro contexto?

`AnimalCard` es reutilizable porque solo recibe datos por props y no depende de una página específica ni de estados globales.  
Una tarjeta similar podría usarse para mostrar productos, cursos, usuarios u otro tipo de información cambiando únicamente los datos que recibe.

---

## 8. ¿Qué elementos del proyecto contribuyen a la accesibilidad? Menciona tres y explica su importancia.

- **Uso de labels en formularios**: ayudan a los lectores de pantalla a identificar los campos.
- **Atributos ARIA**: permiten informar errores o estados dinámicos a usuarios con lectores de pantalla.
- **Foco visible**: facilita la navegación mediante teclado.

---

## 9. Antes de agregar una funcionalidad nueva, ¿qué pasos debes pensar según la filosofía de React?

Se debe analizar qué datos se necesitan, qué estados deben crearse, dónde debe vivir la lógica y cómo se comunicarán los componentes mediante props y eventos.

---

## 10. ¿Qué conceptos de React aprendidos en este proyecto podrías reutilizar en otro tipo de aplicación?

- `useState` para manejar datos dinámicos.
- `useEffect` para cargar información desde APIs.
- Componentes reutilizables.
- Consumo de APIs con Axios.
- Manejo de estados de carga, error y datos vacíos.

#### Nareth Tatiana Ramírez Fuentes
