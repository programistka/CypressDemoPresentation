@title[Easy testing with Cypress]

## @color[black](Easy testing<br>with Cypress<br /><small>Iwona Kubowicz</small>)

@fa[arrow-down text-white]

+++
@snap[midpoint announce-coming-soon text-black]
WHY?
@snapend

+++?image=template/img/before.png
@snap[south-west template-note text-black]
Source: cypress.io
@snapend

+++
@snap[north text-black span-100]
@size[1.5em](Easy to...)
@snapend

@snap[middle fragment]
@ul

-   ...install
-   ...write tests
-   ...debug
-   ...include in CI and CD
    @snapend

+++

```javascript
npm install cypress --save-dev
```

+++?image=template/img/cypress-after-install.png&size=contain

+++?image=template/img/cypress-tree.png&size=contain

+++?image=template/img/todo-1.png&size=contain&position=top

+++?image=template/img/todo-2.png&size=contain&position=top

+++?image=template/img/cypress-tree-with-tests.png&size=contain

+++

```javascript
describe('ToDo test', () => {
    it('Shows item on the list after adding', () => {
        cy.visit('http://localhost:3000');
        cy.get('input[name=addTodoInput]').type('ToDo 1');
        cy.get('button[name=addTodoButton]').click();
        cy.get('ul > li').should('contain', 'ToDo 1');
    });

    it('Removes item from the list when marked as done', () => {
        cy.visit('http://localhost:3000');
        cy.get('input[name=addTodoInput]').type('ToDo 1');
        cy.get('button[name=addTodoButton]').click();
        cy.get('button[name=removeTodoButton]').click();
        cy.get('li').should('not.exist');
    });
});
```

@[1]
@[2]
@[3]
@[4]
@[5]
@[6]
@[9]
@[10-12]
@[13]
@[14]

+++?image=template/img/cypress-open.png&size=contain&position=top

+++?image=template/img/cypress-test-result.png&size=contain&position=top

+++?image=template/img/cypress-test-result-expanded.png&size=contain&position=top

+++
@snap[north text-black span-100]
@size[1.5em](More?)
@snapend

@snap[middle fragment]
@ul

-   recording
-   snapshots
-   real time reloading
-   ... -> <a href="http://cypress.io">cypress.io</a>
    @snapend

+++
@snap[north text-black span-100]
@size[1.5em](Questions?)
@snapend

@snap[west contact-links fragment]
@css[contact-name](Iwona Kubowicz)<br>
<a href="https://twitter.com/programistka">
@fa[twitter-square pad-right-icon]@css[twitter-handle](@programistka)
</a><br>
<a href="mailto: iwona@programistka.com">
@fa[envelope-o pad-right-icon]@css[contact-email](iwona@programistka.com)
</a><br />
<a href="https://programistka.com">
@fa[envelope-o pad-right-icon]@css[contact-web](programistka.com)
</a>
@snapend
