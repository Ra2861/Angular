
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

<hr/>

<h1>Formulario dinâmico</h1>

![image](https://github.com/Ra2861/Angular/assets/99209068/d66693c0-541f-4b86-9f96-b6332bdcfcc3)

<hr/>

Este código implementa um componente Angular chamado DynamicFormComponent que é responsável por criar um formulário dinâmico com base em uma lista de perguntas fornecidas.

![image](https://github.com/Ra2861/Angular/assets/99209068/eedf2ab6-4fb5-47ae-8c97-6e549cdc54d1)

Define o componente DynamicFormComponent com seu seletor, template e provedores de serviço.<br/>
Declara uma entrada @Input() chamada questions que recebe uma lista de perguntas do tipo QuestionBase<string>[].<br/>
Define uma propriedade form do tipo FormGroup que representa o formulário dinâmico.<br/>
Define uma propriedade payLoad para armazenar os dados do formulário após o envio.<br/>
No método ngOnInit(), inicializa o formulário chamando o serviço QuestionControlService para converter a lista de perguntas em um FormGroup.<br/>
No método onSubmit(), converte os valores brutos do formulário em uma string JSON e armazena-os na propriedade payLoad.<br/>

<hr/>

Este trecho do código implementa um componente Angular chamado DynamicFormQuestionComponent que é responsável por renderizar uma única pergunta em um formulário dinâmico.
![image](https://github.com/Ra2861/Angular/assets/99209068/0d347f52-1ae9-4676-915e-2c64b8d9f681)

Define o componente DynamicFormQuestionComponent com seu seletor, template e importações de módulos.
Declara duas entradas @Input():<br/>
question: que recebe uma pergunta do tipo QuestionBase<string>.<br/>
form: que recebe o formulário do tipo FormGroup ao qual a pergunta está associada.<br/>
Define uma propriedade de acesso de leitura chamada isValid, que verifica se o controle do formulário associado à pergunta é válido.<br/>
O template provavelmente contém a marcação HTML para renderizar a pergunta e pode usar as propriedades question e form para exibir as informações e validar a entrada do usuário.<br/>
<hr/> 

Este código define uma classe genérica chamada QuestionBase<T> que serve como modelo para criar perguntas em um formulário dinâmico. Esta classe fornece um modelo flexível para criar diferentes tipos de perguntas, permitindo que as propriedades da pergunta sejam configuradas de forma dinâmica durante a instanciação da classe.

![image](https://github.com/Ra2861/Angular/assets/99209068/7af084d2-3831-409d-9afd-d1812d00e4f5)
Declara várias propriedades que representam os atributos de uma pergunta:

value: o valor da pergunta.
key: a chave da pergunta, que pode ser usada como identificador único.
label: o rótulo ou texto descritivo da pergunta.
required: um indicador booleano que especifica se a pergunta é obrigatória.
order: a ordem em que a pergunta deve aparecer no formulário.
controlType: o tipo de controle usado para representar a pergunta no formulário.
type: o tipo da pergunta (por exemplo, texto, número, opção).
options: uma lista de opções para perguntas de seleção (por exemplo, dropdown, checkbox, radio).
Define um construtor que aceita um objeto de opções como parâmetro. Este objeto de opções permite inicializar as propriedades da pergunta de forma flexível, permitindo que algumas propriedades sejam opcionais.

No construtor, as propriedades são inicializadas com os valores fornecidos no objeto de opções. Se nenhum valor for fornecido para uma propriedade específica, um valor padrão é usado.

<hr />
TextboxQuestion e DropdownQuestion, que representam diferentes tipos de controle. 

![image](https://github.com/Ra2861/Angular/assets/99209068/390ac2fc-0298-401f-8b8a-d6394c1f59fe)

![image](https://github.com/Ra2861/Angular/assets/99209068/a8364d4b-f489-4bba-a8ec-71bb33c9ef5b)

Resumindo, esses códigos definem duas novas classes que herdam da classe QuestionBase. Cada uma dessas classes representa um tipo específico de pergunta: TextboxQuestion representa uma caixa de texto e DropdownQuestion representa um menu suspenso. A propriedade controlType de cada classe é definida de acordo com o tipo de controle que ela representa. Essas classes são usadas para criar instâncias de perguntas com os tipos de controle desejados quando o formulário é renderizado dinamicamente.

<hr/>

Este código define um serviço chamado QuestionControlService que é responsável por criar um FormGroup com base em um array de perguntas (QuestionBase). O serviço possui um método chamado toFormGroup, que recebe um array de perguntas como entrada e retorna um FormGroup.

![image](https://github.com/Ra2861/Angular/assets/99209068/fcf278fe-b15f-49c2-b050-35178a2d327d)

Dentro do método toFormGroup, um loop forEach é utilizado para iterar sobre cada pergunta no array. Para cada pergunta, um novo FormControl é criado com base nos atributos da pergunta, como chave (key), valor (value) e se é obrigatória (required). Se a pergunta for obrigatória, é aplicada a validação Validators.required ao FormControl.

Por fim, todos os FormControls são agrupados em um objeto chamado group, onde a chave de cada FormControl é definida como a chave da pergunta. Esse objeto group é então utilizado para inicializar e retornar um novo FormGroup.

<hr/> 

Este código define um serviço chamado QuestionService, que é responsável por fornecer uma lista de perguntas (QuestionBase) para criar um formulário dinâmico. O método getQuestions() retorna um observable que emite um array de perguntas.
![image](https://github.com/Ra2861/Angular/assets/99209068/21873cc6-d006-462f-bdc4-51029a545035)

Dentro do método getQuestions(), três perguntas diferentes são instanciadas: DropdownQuestion, TextboxQuestion e TextboxQuestion. Cada pergunta é configurada com atributos como chave (key), rótulo (label), valor padrão (value), se é obrigatória (required), tipo de entrada (type), opções (options) para perguntas de seleção e ordem (order).

As perguntas são então agrupadas em um array e ordenadas com base no atributo de ordem (order). O array ordenado é então envolvido em um observable usando o operador of() do RxJS e retornado pelo método getQuestions().
