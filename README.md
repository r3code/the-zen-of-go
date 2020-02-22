﻿# ГО Дзен / Русская версия [The Zen of Go](https://the-zen-of-go.netlify.com)

Десять технических ценностей для написания простого, удобочитаемого и обслуживаемого кода Go.
Представлены на [GopherCon Израиль 2020](http://gophercon.org.il)


## Каждный пакет служит только одной цели

A well designed Go package provides a single idea, a set of related behaviours. A good Go package starts by choosing a good name. Think of your package’s name as an elevator pitch to describe what it provides, using just one word.


## Обрабатывайте ошибки явно

Robust programs are composed from pieces that handle the failure cases before they pat themselves on the back. The verbosity of if err != nil { return err } is outweighed by the value of deliberately handling each failure condition at the point at which they occur. Panic and recover are not exceptions, they aren’t intended to be used that way.


## Возвращайте в начале, а не городите множество вложений 

Every time you indent you add another precondition to the programmer’s stack consuming one of the 7 ±2 slots in their short term memory. Avoid control flow that requires deep indentation. Rather than nesting deeply, keep the success path to the left using guard clauses.


## Оставьте вопросы конкурентного исполнения вызывающей стороне

Let the caller choose if they want to run your library or function asynchronously, don’t force it on them. If your library uses concurrency it should do so transparently.


## Пееред запуском горутины, знай когда она остановится

Goroutines own resources; locks, variables, memory, etc. The sure fire way to free those resources is to stop the owning goroutine.


## Избегайте хранения состояния на уровнн пакета 

Seek to be explicit, reduce coupling, and spooky action at a distance by providing the dependencies a type needs as fields on that type rather than using package variables.


## Простота имеет значение

Simplicity is not a synonym for unsophisticated. Simple doesn’t mean crude, it means readable and maintainable. When it is possible to choose, defer to the simpler solution.

## Write tests to lock in the behaviour of your package’s API

Test first or test later, if you shoot for 100% test coverage or are happy with less, regardless your package’s API is your contract with its users. Tests are the guarantees that those contracts are written in. Make sure you test for the behaviour that users can observe and rely on.


## Если вы думаете, что это медленно, сначала докажите это с помощью теста производительности

So many crimes against maintainability are committed in the name of performance. Optimisation tears down abstractions, exposes internals, and couples tightly. If you’re choosing to shoulder that cost, ensure it is done for good reason.


## Умеренность - это добродетель

Use goroutines, channels, locks, interfaces, embedding, in moderation.


## Способность к поддержке играет роль

Clarity, readability, simplicity, are all aspects of maintainability. Can the thing you worked hard to build be maintained after you’re gone? What can you do today to make it easier for those that come after you?



Насколько это возможно по закону, Давид Чини ([David Cheney](https://dave.cheney.net/)) отказался от всех авторских и смежных или смежных прав на [The Zen of Go](https://the-zen-of-go.netlify.com/).

[<img src="https://i.creativecommons.org/p/zero/1.0/88x31.png">](http://creativecommons.org/publicdomain/zero/1.0/)


Последнее обновление 2020-02-22 21:38:39 UTC  