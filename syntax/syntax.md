
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
