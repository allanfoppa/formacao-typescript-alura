# TYPESCRIPT PARTE 2: AVANÇANDO NA LINGUAGEM

## TEMPLATE

```typescript
template(template: string): string {
  return `${template}`
}

const template = `
  <p>Hello World</p>
`
```

## HERANÇA

### PROTECTED

Só eu view (pai) tenho acesso a esse elemento (propriedade), mas as classes filhas podem acessar.

Sendo impossibilitado de instanciar e manipular...

## GENERICS

```typescript

// MyClass<T> -> Recebe o type no momento em que a classe filha é extendida
// passando o type para a classe pai

// file.ts
export class MyClass<T> {
  // logic
}

// file2.ts
// import .....
export class MyChildClass extends MyClass<string> {
  // logic
}
```

## CLASSE ABSTRATA

Não pode criar uma instancia diretamente nela, apenas se o filho herda. Assim, podendo instanciar.

## MÉTODO ABSTRATO

A classe pai força quem herdou implementar o código

```typescript
export abstract class MyClass<T> {

  // logic

  abstract template(model: T): string;
}
```

## MÉTODOS ESTÁTICOS

Pode ser acessado na classe sem a instância. Sendo chamado diretamente

## ENUMATIONS

```markdown
|├── app
|   ├── enums
|       └── days-of-week.ts
```

```typescript
// days-of-week.ts
export enum DaysOfWeek {
  SUNDAY = 0,
  MONDAY = 1,
  TUESDAY = 2,
  WEDNESDAY = 3,
  THURSDAY = 4,
  FRIDAY = 5,
  SATURDAY = 6
}
```

## OPTIONAL PARAMETERS

```typescript
export class MyClass {
  // logic
  constructor(required: string, optional?: string) {
    //logic
  }
}
```

Apenas os ultimos parâmetros podem ser opcionais no typescript

## EXAMPLE OF tsconfig.json

```json
{
  "compilerOptions": {
      "outDir": "dist/js", // diretório de saída da compilação
      "target": "ES6", // Tipo de código a ser convertido
      "noEmitOnError": true,
      "noImplicitAny": false,
      "removeComments": false,
      "StrictNullChecks": true, // Diz para o compilador TSC que pare de assumir implicitamente o tipo null para todos os tipos da aplicação. Caso null faça sentido, o desenvolvedor deve deixar isso explícito em seu código.
      "experimentalDecorators": true,
      "sourceMap": true, // Habilita colocar breakpoints no arquivo TS e debuggar no navegador "como" o código rodando em TypeScript.
  },
  "include": ["app/**/*"]
}
```
