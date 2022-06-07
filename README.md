# AngularTesting

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

<h1> Configurando JEST no Projeto Angular</h1>
# Angular testing con JEST

1. Remover cualquier referencia de Jasmine / Karma en el package.json
```
npm remove <karma karma-chrome-launcher...>
```

2. Instalar Jest
```
npm install --save-dev jest jest-preset-angular @types/jest
```

3. Crear el ```setup-jest.ts``` en la carpeta root del proyecto y el contenido es el siguiente
```setup-jest.ts
import 'jest-preset-angular/setup-jest';
```

4. Agregar en el package.json, la configuración de Jest
```package.json
"jest": {
    "preset": "jest-preset-angular",
    "setupFilesAfterEnv": [
      "<rootDir>/setup-jest.ts"
    ],
    "globalSetup": "jest-preset-angular/global-setup"
  }
```


4. Configurar JEST en tsconfig.json y tsconfig.spec.json
```tsconfig.json
"types": [
  "jest"
]
```

5. Configurar los comandos para ejecutar las pruebas en el package.json
```package.json
"test": "jest",
"test:watch": "jest --watchAll",
```

6. Remover karma.config.js y el archivo test.ts
