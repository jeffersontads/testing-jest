# AngularTesting

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Running unit tests

Run `npm run test:watch` to execute the unit tests (JEST)

# Angular testing com JEST

1. Remover qualquer referencia de Jasmine / Karma no arquivo package.json
```
npm remove <karma karma-chrome-launcher...>
```

2. Instalar Jest
```
npm install --save-dev jest jest-preset-angular @types/jest
```

3. Crear o ```setup-jest.ts``` na pasta root do projeto com o seguinte conteúdo
```setup-jest.ts
import 'jest-preset-angular/setup-jest';
```

4. Adicionar em package.json, a configuração do Jest
```package.json
"jest": {
    "preset": "jest-preset-angular",
    "setupFilesAfterEnv": [
      "<rootDir>/setup-jest.ts"
    ],
    "globalSetup": "jest-preset-angular/global-setup"
  }
```


4. Configurar JEST no arquivo tsconfig.json e tsconfig.spec.json
```tsconfig.json
"types": [
  "jest"
]
```

5. Configurar os comandos para executar os testes, comando serão configurados no arquivo package.json
```package.json
"test": "jest",
"test:watch": "jest --watchAll",
```

6. Remover karma.config.js e archivo test.ts
