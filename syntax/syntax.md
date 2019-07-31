
Brackets
Escape (to)
Send (to)
Run (to×at)

reader
code

types

«foo»∈Label ※ Label literal
bar∈Bar ⊢ («foo»: bar)∈(«foo»: Bar) ※ Labelled values have the type of the labelling of the labelled value's type

a∈A,b∈B,l∈Label,m∈Label ⊢ (l: a + m: b) ∈ (l: A + m: B)
a∈A,b∈B,l∈Label,m∈Label ⊢ (l: a × m: b) ∈ (l: A × m: B)
a∈A,b∈B ⊢ (a→b) ∈ (A→B)
a∈A,b∈B,l∈Label ⊢ (l: a ⇒ b) ∈ (l: A ⇒ B) ※ A Case



elimination forms have a bit of syntax
※ There also has to be a bit of a destructuring/'algebra' story here
※ Like, you want to be able to do the arms of a + seperately, but the arms of a × together
※ Like if we have a type («Mouse movement»: («dx»: Int × «dy»: Int) + «Mouse click»: («left»: Unit + «middle»: Unit + «right»: Unit))
※ We want to be able to go
※ match x case
※   «Mouse movement»=(«dx»=dx × «dy»=dy) ⇒ print(dx); print(dy);
※   «Mouse click»=
match ... case




base
label type

introduction forms
x=a+b, x=a×b, x=a→b

elimination forms
match x with case a ⇒ b, &a x, x a

μx.μy.(x=ıfoo.ıbar.(foo=3+bar=7)..×y=(x+y))..

&x y ≡ (foo=3+bar=7)
&foo (&x y) ≡ 3
match y cases
  x ⇒ 

x = (a:A≡foo + b:B≡bar)

&a: ∀b.(a×b) → a
a ⇒ b, w ⇒ e, r ⇒ t


+, ×, ⌜a → b⌝, rather than ⌜λa. b.⌝, where ⌜a:A, b:B ⊨ (a → b): (A → B)⌝

+-×÷
^
/

names
_
&...

module terms
  +
  -
  ×
  ÷
  ^
  √
  ‹›
  «»
  ⦇⦈
  ⌜⌝
  ∀
  ∃
  μ
  ı
  _
  □
  ◊
  λ
  Π
  Σ
  &
§

present/absent
‹ › ≡ generic row brackets
«,» ≡ replace , with ×
⦇,⦈ ≡ replace , with +

⌜⌝  ≡ quotation
x → y ≡ x^y
...   ≡ x^(-y)

a×b÷a=b
thing is a name plus a type

selector: ∀X. X ÷ B.
λx.x÷b.


∀x.«&foo: bar, &baz: quux, x»
// data Name = _ | & id
∀x: Name.∀y.«&foo: bar, &baz: quux, x: y»


(a + b) × (x + y)
(a × x) + (a × y) + (b × x) + (b × y)
x^a × x^b ≡ x^(a+b)
(x^m)^n ≡ x^(m×n)
(x→m)→n ≡ x → (m,n)
(x×y)^n ≡ (x^n) × (y^n)

'Indeterminates'
Pattern matching
label+type as a 'selector'
