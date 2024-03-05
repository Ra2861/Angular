![Captura de tela 2024-03-03 232051](https://github.com/Ra2861/Angular/assets/99209068/51f1cbba-2a22-4ee5-a8d7-50c5ada2311a)

Este código implementa um componente Angular chamado DynamicFormComponent que é responsável por criar um formulário dinâmico com base em uma lista de perguntas fornecidas.

Define o componente DynamicFormComponent com seu seletor, template e provedores de serviço.<br/>
Declara uma entrada @Input() chamada questions que recebe uma lista de perguntas do tipo QuestionBase<string>[].<br/>
Define uma propriedade form do tipo FormGroup que representa o formulário dinâmico.<br/>
Define uma propriedade payLoad para armazenar os dados do formulário após o envio.<br/>
No método ngOnInit(), inicializa o formulário chamando o serviço QuestionControlService para converter a lista de perguntas em um FormGroup.<br/>
No método onSubmit(), converte os valores brutos do formulário em uma string JSON e armazena-os na propriedade payLoad.<br/>

![image](https://github.com/Ra2861/Angular/assets/99209068/eedf2ab6-4fb5-47ae-8c97-6e549cdc54d1)


# App
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 17.2.2.

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
