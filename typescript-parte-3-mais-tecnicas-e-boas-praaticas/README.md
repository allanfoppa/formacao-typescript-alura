# Typescript parte 3: mais técnicas e boas práticas

## DECORATORS

É uma função

```markdown
|├── app
|   ├── decorators
|       └── execution-time-log.ts
```

```typescript
export function executionTimeLog() {
    return function(
        target: any, // construtor
        propertyKey: string, // Nome do método
        descriptor: PropertyDescriptor // tem referencias do metodo
    ) {
        const originalMethod = descriptor.value;
        descriptor.value = function(...args: any[]) {
            const t1 = performance.now();
            const originalMethodReturn = originalMethod.apply(this, args);
            const t2 = performance.now();
            console.log(`${propertyKey}, execution time: ${(t2 - t1)/1000} seconds`);
            originalMethodReturn
        };

        return descriptor;
    }
}
```
