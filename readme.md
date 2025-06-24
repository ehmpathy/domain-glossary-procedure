# domain-glossary-procedure

![test](https://github.com/ehmpathy/domain-glossary-procedure/workflows/test/badge.svg)
![publish](https://github.com/ehmpathy/domain-glossary-procedure/workflows/publish/badge.svg)

A declaration of intuitive and unambiguous **Procedure** resources and mechanisms.

# purpose

declare a ubiquitious language for

- resources related to `Procedure`s
  - Procedure

- mechanisms related to `Procedure`s
  - etc

# install

```sh
npm install domain-glossary-procedure
```

# use

### `ProcedureInput`

```ts
  // given: a simple procedure
  const doIt: Procedure<{ reason: string }, void, { done: true }> = (input: {
    reason: string;
  }) => {
    return { done: true };
  };

  // then: can extract the output type
  const reason: ProcedureInput<typeof doIt>['reason'] = '821'; // ✅ knows that reason is a string
  const reason: ProcedureInput<typeof doIt>['reason'] = 821; // 🛑 errors that reason is not a number
```

