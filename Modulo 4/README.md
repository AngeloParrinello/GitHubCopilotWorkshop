[⬅️ Torna indietro](../README.md)

## Modulo 4: Generazione Unit Test e Code Quality

### Esercizio pratico
#### Scenario: Creazione di unit tests per una classe

**Pre requisiti**: creare un file di istruzioni per Copilot indicando i requisiti per la generazione di test unitari. Vedi https://code.visualstudio.com/docs/copilot/copilot-customization
<details>
<summary>Esempio (scegliere in base al linguaggio di programmazione):</summary>

``` 
### ---
applyTo: '**/*.cs'
---
### Instructions
For the unit test generation, please follow these guidelines:
1. **Test Method Naming**: Use the format `MethodName_StateUnderTest_ExpectedBehavior`.
2. **Test Framework**: Use NUnit for the test framework.
3. **Assertions**: Use the constraint model for assertions (e.g., `Assert.That(actual, Is.EqualTo(expected))`).
4. **Comments**: Include comments explaining the purpose of each test.
5. **Edge Cases**: Consider edge cases.

### ---
applyTo: '**/*.js'
---
### Instructions
For the unit test generation, please follow these guidelines:
1. **Test Method Naming**: Use the format `MethodName_StateUnderTest_ExpectedBehavior`.
2. **Test Framework**: Use Jest for the test framework.
3. **Assertions**: Use the expect function for assertions (e.g., `expect(actual).toEqual(expected)`).
4. **Comments**: Include comments explaining the purpose of each test.
5. **Edge Cases**: Consider edge cases.

### ---
applyTo: '**/*.ts'
---
### Instructions
For the unit test generation, please follow these guidelines:
1. **Test Method Naming**: Use the format `MethodName_StateUnderTest_ExpectedBehavior`.
2. **Test Framework**: Use Jest for the test framework.
3. **Assertions**: Use the expect function for assertions (e.g., `expect(actual).toEqual(expected)`).
4. **Comments**: Include comments explaining the purpose of each test.
5. **Edge Cases**: Consider edge cases.
```
</details></br>

#### Obiettivi dell'esercizio:
1. Generare unit test tramite la chat di Copilot
2. Generare unit test tramite l'editor inline chat di Copilot
3. Affinare i prompt per ottenere risultati migliori
4. Coprire i casi limite
5. Comprendere il funzionamento del file di istruzioni per Copilot

Inizia aprendo il file di test presente in `Modulo 4/Esercizio/` e procedi con la generazione dei test unitari per la classe `TaskList`. Utilizza sia la chat di Copilot che l'editor inline chat per generare i test.

## Tips:
**Obiettivo**: imparare a generare test unitari in modo efficace utilizzando Copilot.

### Scrivi prompt precisi e mirati
Quando chiedi a Copilot di generare unit test, contestualizza sempre la richiesta. Specifica:
- Cosa deve essere testato (es. Add)
- Quale comportamento ti aspetti
- Eventuali casi limite da considerare
- Aggiungere al contesto la classe da testare

```
/test generate unit tests for the Add method in the Calculator class. The method should handle both positive and negative numbers, and edge cases like zero and null inputs. Ensure that the tests cover all possible scenarios.
```

### Raffina i prompt quando i risultati non ti convincono
Se i test generati non sono utili, non cambiare tutto subito: correggi solo il prompt. Puoi guidare Copilot così:
```
/test refine the unit tests for the addTask method in the TaskList class. Ensure that edge cases are covered, such as adding a null task or an empty task
```

### Usa il file di istruzioni per migliorare la qualità dei test
Il file `.github/copilot-instructions.md` consente di definire le regole che Copilot seguirà nella generazione dei test. Ad esempio:
- Convenzioni di naming (Method_State_Expected)
- Framework da usare (NUnit, Jest, ecc.)
- Stile delle asserzioni
- Inclusione di commenti e edge case

Il file di istruzioni serve a far capire a Copilot lo stile e gli standard attesi nel tuo progetto. Non sovrascrive il codice esistente, ma ne influenza la generazione. Questo è particolarmente utile per grandi progetti dove serve coerenza nei test.

Assicurati che le istruzioni siano già presenti prima di generare test.

### Link utili:
- [Generazione di unit test](https://docs.github.com/en/copilot/using-github-copilot/guides-on-using-github-copilot/writing-tests-with-github-copilot)
- [File di istruzioni](https://docs.github.com/en/copilot/chat/using-copilot-chat/copilot-chat-instructions-file)