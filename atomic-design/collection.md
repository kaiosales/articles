# Collection
## Overview
Designed to display a collection of a representation of an entity, that allows bulk actions and filtering on that collection.
This template is not particularly bound to any specific entity representation and can be used to host multiple ones as long as they support bulk 
actions and filtering as well.

[badge-error]: https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/error.svg 'DON'T'
> ![badge-error][badge-error]<br>
> Create a list container component for each collection representation of an entity

[badge-check]: https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/check.svg 'DO'
> ![badge-check][badge-check]<br>
> Create a single list container component that contains a switcher that can toggle between each collection representation


## Concept
### Dataflow
<table border="0">
 <tr>
    <td>![Context Initialization](../assets/images/context-initialization.png "Context Initialization")</td>
    <td>[SOURCE](https://sequencediagram.org/index.html?presentationMode=readOnly#initialData=C4S2BsFMAIEZoLTQMIHsB2wCGJ2QE7S5ghbggBeWoGAULQEarDCoC2ADlvqAMYhdMAZ1pceIfoODQAxMgDMABkUAmAGLQARADpdacFF410aTDjz5N0LEOgBxI-lPZcBUdz4CsmWVgAcKgCcvPIAXPCaaJwYkJgAyqz4kFY2KBguFgmoSe7ikt7SMmpqyACCKn5aAKpCBHEEAG4Syda2AJLoTdjGzpAAHsD1+E28kLmeUrKqfn4AIvD6hsaz1FhDI2NiEwVTFXMLqAaQRiAYK9hZ+FgA5pDrzfTkAGaQ5HhCwACeUPaOzuYEWQKZTqcKhAAmNgAFpBwbQsCcGsdDtlfsAnOkAYQ5EpVGpHiAXm9IB9vjB-q58JcYDJ-EEQmDIUIYXCEaAkbwUYQKZlEjS6cF5ASia5ST8Ol1qKcTOl+oNGs1ZMUyhVGdDYfDEcjwKiJWApRhegN7qMlSVyn5ha9RV8fotjstViaadN9mrmRq2SAOVy0kcTmcnQrTTJXfMrcSxeTDktpec1okbndgy69vN3SzNeztaj7QH0PHLknnbsZuH4QBXVhehoG9DQOi0BzonkEBAAPmbGLMlNC6GuAHl0B0wPQu638B2J9TQsRQGRKGNwZAa9QV09gIDx5jKfRp3yO+29d1pUb5cNmqEAO5gKEAGTXHzU+HYAApeBX8ElMDUCAASABKWhjzrM9nQQQ992ySBQgAHlgitanwdt21oKCkinHdeWg0IkmuEAPgIOxIGAM96GXVdNywDdAXQsY6MwntsKSXDIHwwiqRIsiKMRNdqM3bksLqPk0KEqkD3bPNHQuFNZ3QEgFwoSBX0hbAgNoHVUA4aBbFQJ4dNQT9RmdIQAG0AF09xjB04yDC9Rkw-1pITbJi1koRtCSLBwWfdg4kM-BRlfdTRKc2yLkTW5wMc2NAxk+yYOAKECO0D8v1iaQAF4-VimVMDlbQ2AIW4VNWAAaIh5PncB1NiOFQtywsUximy4rWWSkpStLvyynLWryzcBkK4rlNUrAKrnUgatoHj2T4mjBLCtrnQa-qmoSlr83WjZQk6jyPjXOIKwYAArB1tDwAZXz21LPx6oDZu9eaBL6ra7I2eggA)</td>
 </tr>
 <tr>
    <td>Lorem ipsum ...</td>
    <td>Lorem ipsum ...</td>
 </tr>
</table>
### ComponentStore
Currently, our implementation uses the concept of [ComponentStore](https://ngrx.io/guide/component-store).
The reasoning behind this choice was that this would be an intermediate step toward a full global Store shared across the entire application, 
however in order to manage the complexity of this transition in the whole code base, ComponentStore offers a nice middle ground while 
increasing the team’s know-how in reactive component coding style.

In the future once all UIs were migrated to ComponentStore, we can easily introduce the global Store with very little code change and no 
paradigm change making the transition way smoother

### Marble testing
Our store is completely *Observables* based, thus there is two main test patterns that can be used: “**subscribe and assert**” and “**marbles))” ([more on those patterns](https://medium.com/angular-in-depth/how-to-test-observables-a00038c7faad)).

In our case we are using [marble testing](https://rxjs.dev/guide/testing/marble-testing) strategy to not only be able to test asynchronous code but also in order to align with industry standards 
and to drive more a deeper understanding of Observables.

All the test is done without any external library, relying solely on `TestScheduler` from `rxjs/testing`.

## Implementation
### Naming convention
All components created using this template should have the following name convention:
> **\<entity\>**-collection-container

Where **\<entity\>** is a business entity/concept that have a visual representation
### Dependencies
#### Libraries
#### Modules
### Structure
### Files
#### *.module.ts
#### *.component.html
#### *.component.ts
#### *.component.stories.ts
#### *.store.ts
##### Standards
#### *.store.spec.ts