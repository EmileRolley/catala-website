+++
title = "Formalization"
+++

## Surface syntax

The syntax of the langage is derived from the [parser source file](https://github.com/CatalaLang/catala/blob/master/compiler/surface/parser.mly) using [Obelisk](https://github.com/Lelio-Brun/Obelisk). This syntax is language-agnostic, meaning that it is valid for
both English and French versions of Catala. Indeed, the language only affects
the tokens, not
their order.

<details>
  <summary>Expand</summary>

```xml
          <typ_base> ::= INTEGER
                       | BOOLEAN
                       | MONEY
                       | DURATION
                       | TEXT
                       | DECIMAL
                       | DATE
                       | <constructor>

 <collection_marked> ::= COLLECTION

               <typ> ::= <typ_base>
                       | <collection_marked>

            <qident> ::= <ident>+,DOT
```

</details>

<br>

To complement this formal description of the syntax, a cheat sheet is also
available and is probably more practical to satisfy your hands-on syntax
curiosity.

<button class="btn btn-primary btn-md px-4 mb-2 center">
  Access the syntax cheat sheet
</button>

## Core semantics

Catala's unique feature is the possibility to give multiple definitions to the
same variable, each definition being conditionned to a logical guard. If the
guard is true, then the definition is applicable. This behavior is adapted to
the style in which legal statutes are redacted. In the case of multiple guards
being true at the same time, the definition is picked according to a precedence
in the definitions that is specified in the source code.

<button class="btn btn-primary btn-md px-4 mb-2">
  Access the complete formalization paper
</button>
