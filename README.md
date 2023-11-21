# Digital Style Guide :alien: :nail_care:

## ESLint - ¿Qué es y por qué es importante?

ESLint es una herramienta de linting para JavaScript que ayuda a identificar y corregir errores en el código, así como a aplicar y mantener un estilo de código consistente. A continuación, se explican algunos 


#Puntos clave sobre ESLint :point_down:

1. **Detección de Errores y Problemas de Estilo:**
   - ESLint analiza el código en busca de errores, problemas de estilo y posibles vulnerabilidades.
   - Ayuda a prevenir errores comunes antes de que lleguen a ejecutarse, mejorando la calidad del código.
  
      ![descarga](https://github.com/OscarBGrandeG/style_guide/assets/98411972/c20908e1-c84a-478c-a8b2-489a7369a0a8)

3. **Consistencia en el Estilo de Código:**
   - Define reglas y estándares de codificación que pueden adaptarse a las necesidades del equipo.
   - Facilita la creación de código consistente, independientemente del número de desarrolladores en el equipo.

4. **Facilita la Colaboración:**
   - Al seguir un conjunto común de reglas, ESLint facilita la colaboración entre miembros del equipo.
   - Reduce las discusiones sobre el estilo de código durante revisiones de código.
  
      ![peterp](https://github.com/OscarBGrandeG/style_guide/assets/98411972/4eb3d5f5-cb4a-41f0-baea-670f8fc59078)

5. **Mejora la Legibilidad del Código:**
   - Al identificar y corregir problemas de estilo, ESLint contribuye a mejorar la legibilidad del código.
   - Un código más legible facilita el mantenimiento y la comprensión del mismo.
  
      ![esoagueti](https://github.com/OscarBGrandeG/style_guide/assets/98411972/6343c700-34e0-4040-973c-ae2ed351b51b)

6. **Aumenta la Eficiencia del Desarrollo:**
   - Detecta problemas de forma temprana, reduciendo la cantidad de errores que se pueden introducir en el código.
   - Mejora la eficiencia del desarrollo al proporcionar retroalimentación rápida sobre posibles problemas.
  
     ![images](https://github.com/OscarBGrandeG/style_guide/assets/98411972/322311be-1827-474c-a752-a743989271db)


7. **Configuración Personalizada:**
   - ESLint es altamente configurable, lo que permite a los equipos adaptar las reglas según las necesidades específicas del proyecto.
   - La configuración personalizada permite definir estándares de codificación específicos para un proyecto.

8. **Integración con Herramientas de Desarrollo:**
   - Puede integrarse fácilmente con herramientas de desarrollo y flujos de trabajo como editores de texto, IDEs y sistemas de integración continua (CI).
   - La integración en el flujo de trabajo mejora la coherencia y la eficiencia del desarrollo.

   ![images](https://github.com/OscarBGrandeG/style_guide/assets/98411972/2a61fa8a-e7a1-436d-b4c1-67aab6266b44)

En resumen, ESLint es una herramienta esencial ya que contribuye a la calidad del código al detectar errores, mantener la consistencia y mejorar la eficiencia del desarrollo.


# Configuración de ESLint en Proyectos ReactJS

## Paso 1: Instalar ESLint

Para instalar ESLint en tu proyecto, ejecuta el siguiente comando en la terminal:

```bash
npm install eslint --save-dev

o

yarn add eslint --dev
```

## Paso 2: Crea un archivo de configuración .eslintrc.js en la raíz de tu proyecto. Puedes utilizar un archivo de configuración predeterminado o personalizarlo 

```bash
Ejemplo de archivo .eslintrc.js

module.exports = {
  extends: 'eslint-config-react-app',
};
```

## Paso 3: Añade los siguientes scripts a tu archivo package.json para ejecutar ESLint

```bash
"scripts": {
  "lint": "eslint src",
  "lint:fix": "eslint --fix src"
}
```

## Paso 4: Añade los siguientes scripts a tu archivo package.json para ejecutar ESLint

- Instala la extensión ESLint para tu editor de código.

![Captura de pantalla 2023-11-21 a la(s) 11 41 55](https://github.com/OscarBGrandeG/style_guide/assets/98411972/ce14718e-5c2f-47a8-b2e7-bbd57e36076f)

## Paso 5: Ejecutar ESLint

```bash
npm run lint
o
yarn lint


npm run lint:fix
o
yarn lint:fix
```
