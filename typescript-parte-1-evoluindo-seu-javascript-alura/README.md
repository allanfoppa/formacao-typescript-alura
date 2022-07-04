# TypeScript parte 1: evoluindo seu JavaScript

## GENERICS

```typescript
export class MyClassList {

  private myAttribute = [] // wrong (Generic type 'Array<T>' requires 1 type argument(s))
  private myAttribute: Array<MyClass> = [] // correct

  // others examples:
  private myAttributeNumber: Array<number> = [] // don't accepts string, Date
  private myAttributeString: Array<string> = [] // don't accepts number, Date
}
```

## MODIFICADOR READONLY

Quando "setado" com o tipo `ReadOnly`, isso quer dizer que não pode ser dado um novo valor.

Consulte do utilitário [aqui.](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)

Ex:

```typescript
public listMethod(): ReadonlyArray<MyClass> {
  return this.MyClassList // add MyClassList to const
}
```

## TYPESCRIPT'S SYNTACTIC SUGAR

```typescript
export class MyClassList {

  // WITH ATTRBUTE
  // 1º option = Array<MyClass>
  // 2º option = MyClass[]
  private myAttribute: MyClass[] = []

  // WITH METHOD
  // 1º option = Array<MyClass>
  list(): ReadonlyArray<MyClass> {
    // logic
  }
  // 2º option = MyClass[]
  list(): readonly MyClass[] {
    // logic
  }
}
```
