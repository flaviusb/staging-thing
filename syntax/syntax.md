No lambda. Just patterns/copatterns and equations. Mu gives you a name.

μleft right. ıa b. left a b = right b a = a.

μleft right. {
  ıa b.
  pattern: left a b
  pattern: right b a
  copattern: a
}


What is a name vs a projection/selection?

scope
equations



Models are a tuple (Names, Entities) that operates like a Map from Name to Entity. Models are created with sprout. Scope under binding cooccurs with the extent of a quantifier.

anaphora = sprout()


(∃x y z) { }




Note to self: scopes as Containers

note to self: holes in containers as a way to have linear scopes that can be extended or sealed.

note to self: sprout, prune, take. scopes as lightweight but explicitly instantiated. Modules as functions that take ∃ types and generate a scope - that is, the combination of ∃, →, type, and sprout. μ is something else, and is used for eg tying together explicit instantiations of modules.


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

Label
Labelled
Row
Product
Sum


μf. f = ıx∈Number. x → x + 1.
μf. ıx∈Number. f x = x + 1.


(_ &_) ∈ ∀r∈Product l∈Label a. where (r\l). (l: a × r) → l → a.
(_−_)  ∈ ∀r∈Product l∈Label a. where (r\l). (l: a × r) → l → r.

Commutation and distribution of + and × 

syntax sugar: when you have a label by itself in a sum type, that expands to label: Unit.


Current status: ⌜∀x.ıy∈x.μoption∈(«some»: x + «none»:⬢ ).μsome∈x→option.μnone∈option. some y = («some»: y). none = («none»:⬢ ).⌝


elimination forms have a bit of syntax
※ There also has to be a bit of a destructuring/'algebra' story here
※ Like, you want to be able to do the arms of a + seperately, but the arms of a × together
※ Like if we have a type («Mouse movement»: («dx»: Int × «dy»: Int) + «Mouse click»: («left»: Unit + «middle»: Unit + «right»: Unit))
※ We want to be able to go
※ match x case
※   «Mouse movement»=(«dx»=dx × «dy»=dy) ⇒ print(dx); print(dy);
※   «Mouse click»=
match ... case

\match
  ıdx «Mouse movement»=(«dx»=dx × «dy»=7) ⇒ {
      print dx.
  }.
  ımm∈(«dx»: Int × «dy»: Int) «Mouse movement»=mm ⇒ {
    print (mm &«dx»).
    print (mm &«dy»).
  }.
  «Mouse click»=«left» ⇒ {
  }


modules have a name and free variables for threading through stuff; you can do mutual stuff by importing the modules under a mu

There is no 'global scope; each module can only see its internals plus whatever it imported. For modules that depend on each other, you need an ur-module that imports them both under a mu

module $name 



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
  «»
  ‹›
  ⦇⦈
  {}
  ⦃⦄
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
⦃,⦄ ≡ replace , with ×
⦇,⦈ ≡ replace , with +

«» ≡ literal label
⌜⌝ ≡ quotation
{} ≡ code blocks 
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
