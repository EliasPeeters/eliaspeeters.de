---
type: post
title: Racket examples
description: Racket examples
author: Elias Peeters
categories:
  - Racket
tags:
  - Racket
  - test
date: 2020-02-20
linktitle: ""
---
<!-- 
+++
author = "Elias Peeters"
categories = ["Racket"]
tags = ["Racket", "test"]
date = "2020-02-20"
description = "Racket examples"
linktitle = ""
title = "Racket examples"
type = "post"

+++ -->

# A list of example programms that may be helpful

This is just a collection with programms in racket. These solutions may not be perfect but maybe they can help somebody in need 😉.

### Theater costs
An old-style movie theater has a simple profit function. Each customer pays $5 per ticket. Every performance costs the theater $20, plus $.50 per attendee. Develop the function total-profit. It consumes the number of attendees (of a show) and produces how much income the attendees produce. 

```rktl
(define costsTheater 20)

(define incomeAttendees
  (lambda [anzahl]
    (* anzahl 5)))

(define costsAttendees
  (lambda [anzahl]
    (* anzahl 0.5)))

(define total-profit
  (lambda [anzahl]
    (- (incomeAttendees anzahl) costsTheater (costsAttendees anzahl))))
```

### Tax calculation
Develop the function tax, which consumes the gross pay and produces the amount of tax owed. For a gross pay of $240 or less, the tax is 0%; for over $240 and $480 or less, the tax rate is 15%; and for any pay over $480, the tax rate is 28%. 

```rktl
(define tax
  (lambda [value]
    (cond
      [(< value 240) value]
      [(< value 480) (+ 240 (* (- value 240) 0.85))]
      [else (+ 240 (* (- 480 240) 0.85) (* (- value 480) 0.72))])))
```