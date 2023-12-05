# Digital Style Guide :alien: :nail_care:

## ESLint - ¿Qué es y por qué es importante?

ESLint es una herramienta de linting para JavaScript que ayuda a identificar y corregir errores en el código, así como a aplicar y mantener un estilo de código consistente. A continuación, se explican algunos

#Puntos clave sobre ESLint :point_down:

1. **Detección de Errores y Problemas de Estilo:**

   - ESLint analiza el código en busca de errores, problemas de estilo y posibles vulnerabilidades.
   - Ayuda a prevenir errores comunes antes de que lleguen a ejecutarse, mejorando la calidad del código.

     ![descarga](https://github.com/OscarBGrandeG/style_guide/assets/98411972/c20908e1-c84a-478c-a8b2-489a7369a0a8)

2. **Consistencia en el Estilo de Código:**

   - Define reglas y estándares de codificación que pueden adaptarse a las necesidades del equipo.
   - Facilita la creación de código consistente, independientemente del número de desarrolladores en el equipo.

3. **Facilita la Colaboración:**

   - Al seguir un conjunto común de reglas, ESLint facilita la colaboración entre miembros del equipo.
   - Reduce las discusiones sobre el estilo de código durante revisiones de código.

     ![peterp](https://github.com/OscarBGrandeG/style_guide/assets/98411972/4eb3d5f5-cb4a-41f0-baea-670f8fc59078)

4. **Mejora la Legibilidad del Código:**

   - Al identificar y corregir problemas de estilo, ESLint contribuye a mejorar la legibilidad del código.
   - Un código más legible facilita el mantenimiento y la comprensión del mismo.

     ![esoagueti](https://github.com/OscarBGrandeG/style_guide/assets/98411972/6343c700-34e0-4040-973c-ae2ed351b51b)

5. **Aumenta la Eficiencia del Desarrollo:**

   - Detecta problemas de forma temprana, reduciendo la cantidad de errores que se pueden introducir en el código.
   - Mejora la eficiencia del desarrollo al proporcionar retroalimentación rápida sobre posibles problemas.

     ![images](https://github.com/OscarBGrandeG/style_guide/assets/98411972/322311be-1827-474c-a752-a743989271db)

6. **Configuración Personalizada:**

   - ESLint es altamente configurable, lo que permite a los equipos adaptar las reglas según las necesidades específicas del proyecto.
   - La configuración personalizada permite definir estándares de codificación específicos para un proyecto.

7. **Integración con Herramientas de Desarrollo:**

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

**Paso 2: Crea un archivo de configuración .eslintrc.js en la raíz de tu proyecto. Puedes utilizar un archivo de configuración predeterminado o personalizarlo**

```bash
Ejemplo de archivo .eslintrc.js

module.exports = {
  extends: 'eslint-config-react-app',
};
```

**Paso 3: Añade los siguientes scripts a tu archivo package.json para ejecutar ESLint**

```bash
"scripts": {
  "lint": "eslint src",
  "lint:fix": "eslint --fix src"
}
```

**Paso 4: Añade los siguientes scripts a tu archivo package.json para ejecutar ESLint**

- Instala la extensión ESLint para tu editor de código.

   ![Captura de pantalla 2023-11-21 a la(s) 11 41 55](https://github.com/OscarBGrandeG/style_guide/assets/98411972/ce14718e-5c2f-47a8-b2e7-bbd57e36076f)

**Paso 5: Ejecutar ESLint**

```bash
npm run lint
o
yarn lint


npm run lint:fix
o
yarn lint:fix
```
![elmoexp](https://github.com/OscarBGrandeG/style_guide/assets/98411972/f8349a28-f09d-4712-b42a-0258429b5895)

#Aquí te dejo unas reglas básicas de ESLint para React

```bash
Reglas Básicas para React:

module.exports = {
  extends: ['eslint-config-react-app'],
  rules: {
    // Aquí puedes agregar reglas específicas para tu proyecto React
  },
};

Evitar el Uso de console en Producción:

rules: {
  'no-console': process.env.NODE_ENV === 'production' ? 'error' : 'warn',
}

Evitar el Uso de alert:

rules: {
  'no-alert': 'error',
}

Evitar Variables No Utilizadas:

rules: {
  'no-unused-vars': 'warn',
}

Limitar la Longitud de las Líneas:

rules: {
  'max-len': ['warn', { code: 80, ignoreUrls: true }],
}

Usar Punto y Coma:

rules: {
  semi: ['error', 'always'],
}

Indentación de Dos Espacios:

rules: {
  indent: ['error', 2],
}

Ordenar las Importaciones de React:

rules: {
  'react/jsx-uses-react': 'error',
  'react/jsx-uses-vars': 'error',
}
```

#Evitar Anti-Patrones y Malas Prácticas

![homeroceb](https://github.com/OscarBGrandeG/style_guide/assets/98411972/be35d320-1aa0-4c64-8c8b-88f1552b64c9)

```bash
Evitar el Uso Directo de setState en Funciones Asíncronas:

// Anti-patrón
async function fetchData() {
  const data = await fetchDataFromAPI();
  this.setState({ data });
}

// Mejor práctica
async fetchData() {
  const data = await fetchDataFromAPI();
  if (this._isMounted) {
    this.setState({ data });
  }
}

componentDidMount() {
  this._isMounted = true;
}

componentWillUnmount() {
  this._isMounted = false;
}

Evitar el Uso de index como Key en Listas:

// Anti-patrón
{items.map((item, index) => (
  <MyComponent key={index} data={item} />
))}

// Mejor práctica
{items.map((item) => (
  <MyComponent key={item.id} data={item} />
))}

Evitar el Uso de dangerouslySetInnerHTML:

// Anti-patrón
function MyComponent({ htmlContent }) {
  return <div dangerouslySetInnerHTML={{ __html: htmlContent }} />;
}

// Mejor práctica
function MyComponent({ htmlContent }) {
  return <div>{ReactHtmlParser(htmlContent)}</div>;
}

Evitar el Uso de any en TypeScript sin Justificación:


// Anti-patrón
const variable: any = "Hola, soy de tipo 'any'.";


// Mejor práctica
const variable: string = "Hola, soy de tipo 'string'.";


Evitar Lógica Compleja en el Render:

// Anti-patrón
function MyComponent({ data }) {
  return (
    <div>
      {data && data.length > 0 && (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      )}
    </div>
  );
}

// Mejor práctica
function MyComponent({ data }) {
  const hasData = data && data.length > 0;

  return (
    <div>
      {hasData && (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      )}
    </div>
  );
}
```

## Herramientas Adicionales

![homersino](https://github.com/OscarBGrandeG/style_guide/assets/98411972/8072e1b8-a63f-4198-8582-0e0e826573ce)

1. **Prettier**

   - Es una herramienta de formateo de código que ayuda a mantener la consistencia en la apariencia de tu código fuente. Su objetivo principal es formatear automáticamente el código de manera consistente según un conjunto de reglas predefinidas, lo que ayuda a un estadard sobre estilos de código y a mantener un código más limpio y legible.

   - Algunas características y usos comunes de Prettier incluyen:
     1. Formateo Automático
     2. Consistencia en Estilos de Código
     3. Integración con Editores de Código
     4. Admite Múltiples Lenguajes
     5. Configuración Personalizable
     6. Integración con Procesos de Construcción y CI/CD

    **Ejemplo**

    ```bash
    {
      "semi": false, // No añadir punto y coma al final de las declaraciones
      "singleQuote": true, // Utilizar comillas simples en lugar de comillas dobles
      "tabWidth": 4, // Tamaño de la tabulación
      "useTabs": false, // Utilizar espacios en lugar de tabulaciones
      "printWidth": 120, // Ancho máximo de línea
      "arrowParens": "always", // Incluir paréntesis alrededor de los argumentos de las funciones de flecha
      "bracketSpacing": true, // Añadir espacios alrededor de los corchetes en objetos
      "jsxBracketSameLine": false, // Colocar el corchete de cierre JSX en una nueva línea
      "jsxSingleQuote": false, // Utilizar comillas simples en JSX
      "quoteProps": "as-needed", // Añadir comillas solo cuando sea necesario en los nombres de las propiedades de los objetos
      "trailingComma": "all", // Añadir una coma al final de las listas y objetos
      "endOfLine": "auto" // Utilizar saltos de línea UNIX o Windows automáticamente
    }
    ```

    **Instalación**

  ```bash
    npm install --save-dev prettier
    o
    yarn add --dev prettier
  ```

- Te puedes apoyar del plugin que te proporciona Visual Studio Code
  ![Captura de pantalla 2023-11-21 a la(s) 12 06 18](https://github.com/OscarBGrandeG/style_guide/assets/98411972/b805b044-7b3e-4d85-b0ed-d9f795caf81e)

2. **Husky y lint-staged**

   - Husky: Es una herramienta que te permite configurar hooks de Git de manera fácil y estructurada. Se utiliza para ejecutar comprobaciones de calidad de código, pruebas, o cualquier tarea personalizada antes de que se confirme el código.
  
   - Lint-staged: Se utiliza en combinación con Husky para ejecutar tareas específicas, como el formateo de código o la ejecución de linters, solo en los archivos que se han modificado y se están preparando para hacer commit. Esto ayuda a mantener la consistencia y calidad del código que se envía al repositorio.
  
   **Instalación**

   ```bash
   npm install --save-dev husky lint-staged
   o
   yarn add --dev husky lint-staged
   ```

   **Ejemplo**

   - Agrega configuración en tu package.json
   ```bash
      "husky": {
        "hooks": {
          "pre-commit": "lint-staged"
        }
      },
      "lint-staged": {
        "linters": {
          "src/**/*.{js,jsx}": ["eslint --fix", "git add"]
        }
      }
   ```
4. **React DevTools**

   - React DevTools es una extensión del navegador que te permite inspeccionar y depurar tus componentes React en el navegador (es una extensión de Chrome).

5. **Jest**

   - Es un framework de prueba que se utiliza comúnmente en proyectos React. Se integra bien con React y proporciona funciones como pruebas unitarias, cobertura de código y pruebas de componentes.

6. **VSCode setting.json**

   - El archivo settings.json es un archivo de configuración que te permite personalizar y ajustar diversos aspectos del entorno de desarrollo.

  ```bash
  {
    // =======================
    // Apariencia y Comportamiento
    // =======================
    "tabnine.experimentalAutoImports": true,
    "workbench.iconTheme": "material-icon-theme",
    "workbench.colorTheme": "Atom One Dark",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
      "source.fixAll": true
    },
    "typescript.enablePromptUseWorkspaceTsdk": true,
    "editor.tabSize": 2,
    "editor.fontSize": 14,
    "window.restoreFullscreen": true,
    "workbench.editor.tabSizing": "shrink",
    "breadcrumbs.enabled": false,
    "explorer.openEditors.visible": 0,
    "editor.tabCompletion": "on",
    "editor.cursorBlinking": "phase",
    // =======================
    // Búsqueda y Exclusión
    // =======================
    "search.exclude": {
      "**/node_modules": true,
      "**/*.code-search": true,
      "ios/": true,
      "android/": true,
      "dist/": true,
      "yarn.lock": true,
      "package-lock.json": true,
      ".gitignore": true,
      ".expo": true,
      ".vscode": true
    },
    // =======================
    // Prettier y Formateo
    // =======================
    "javascript.validate.enable": false,
    "prettier.singleQuote": true,
    "prettier.jsxSingleQuote": true,
    "prettier.trailingComma": "none",
    "prettier.arrowParens": "avoid",
    "prettier.proseWrap": "preserve",
    "prettier.quoteProps": "as-needed",
    "prettier.bracketSpacing": true,
    "prettier.tabWidth": 2,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    // =======================
    // Lenguajes Específicos
    // =======================
    "[markdown]": {
      "editor.quickSuggestions": {
        "comments": "on",
        "strings": "on",
        "other": "on"
      }
    },
    "[json]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[javascript]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[javascriptreact]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[typescript]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[typescriptreact]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[jsonc]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "[html]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "javascript.updateImportsOnFileMove.enabled": "always",
    "security.workspace.trust.banner": "never",
    "emmet.includeLanguages": {
      "typescript": "typescriptreact",
      "javascript": "javascriptreact"
    },
    "typescript.updateImportsOnFileMove.enabled": "always",
    "typescript.tsserver.log": "off",
    // =======================
    // ESLint y Validación
    // =======================
    "eslint.enable": true,
    "eslint.validate": [
      "javascript",
      "javascriptreact",
      "typescript",
      "typescriptreact"
    ]
  }
  ```

# Material de apoyo (buena practicas)

[Airbnb style guide] (https://github.com/airbnb/javascript)
