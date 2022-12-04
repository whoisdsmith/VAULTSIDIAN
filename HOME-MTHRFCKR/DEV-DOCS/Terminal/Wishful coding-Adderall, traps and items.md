# Wishful coding: Adderall, traps and items

I have been pondering over some ideas about traps, items and how to represent what kind of effects they have in-world. I might be over thinking this a bit and going for too general and flexible solution, when simpler solution would work just fine. Currently this isn’t that urgent yet, as there are only few monsters and two types of traps (pits and caltrops). Monsters are too stupid to avoid either one. For caltrops it sort of makes sense, but they really should be able to spot huge pits and go around.

A bit of background. There’s a Hy implementation of [miniKanren](http://minikanren.org/) called [adderall](https://github.com/algernon/adderall). I blogged about it [here](https://engineersjourney.wordpress.com/tag/adderall/) previously. The idea is that with miniKanren language one can represent relations and certain constraints of entities and reason about them. The goals that define these relations aren’t one-way, but can run in both direction. For example, if I have goal breakfastᵒ, that defines that with bacon I like to drink tea and with oatmeal I prefer coffee:

1

2

3

`(defn breakfastᵒ [meal drink]`

`  ``(condᵉ [(≡ meal 'bacon) (≡ drink 'tea)]`

`         ``[(≡ meal 'oatmeal) (≡ drink 'coffee)]))`

I can then query what I would drink, if I eat bacon:

1

2

3

`=> (run* [q]`

`...      (breakfastᵒ 'bacon q))`

`['tea']`

But I can also check what to eat if I have coffee:

1

2

3

`=> (run* [q]`

`...      (breakfastᵒ q 'coffee))`

`['oatmeal']`

Or what all kinds of possible combinations I can have:

1

2

3

4

5

`=> (run* [q]`

`...      (fresh [meal drink]`

`...             (breakfastᵒ meal drink)`

`...             (≡ q (, meal drink))))`

`[('bacon', 'tea'), ('oatmeal', 'coffee')]`

Or even if some combination of choices matches my preferences:

1

2

3

4

`=> (run* [q]`

`...      (condᵉ [(breakfastᵒ 'bacon 'tea) (≡ q "bacon and tea is fine")]`

`...             [(breakfastᵒ 'bacon 'coffee) (≡ q "bacon and coffee is fine")]))`

`['bacon and tea is fine']`

And since adderall is just a dsl on top of Hy, I can use it easily with other lisp code:

1

2

3

4

5

6

7

8

9

`=> (defn select-drink [meal]`

`...  (first (run* [q] (breakfasto meal q))))`

`=> (select-drink 'bacon)`

`'tea'`

`=> (select-drink 'eggs)`

`=> (select-drink 'oatmeal)`

`'coffee'`

System is quite flexible, although writing goals is something I really strugle. More often than not I end up with infinite recursion and the whole concept is so different from anything I have ever tried before. But what does this have to do with traps and items? Am I planning to kill players with overload of bacon and hide their bodies in ponds of cold coffee?

Nothing of that sorts. I just have a nascent idea that maybe it would be possible to build high level AI that reasons about its surroundings, without having to specifically code in that a certain item can be used to bypass certain obstacles. If there is a trap and AI has items to bypass that trap, it maybe should use them or decide to go around the trap (depending on the situation). These would be high level decisions, leading to intermediatery goals that different AI routines can be used to achieve.

For this scheme to work, I need a way to code not only items and their effects, but also things like walking excerts force on ground, while flying doesn’t and stepping on a trigger plate will trigger a trap and cause damage. From there the system hopefully can infer that flying over a trap is much better idea than walking through it. It hopefully would help with questions like “can I heal myself somehow? What is the fastest way of getting out of this situation?” and such in the long run.

How would I go about representing all these relations and goals? If I have learned anything about programming, it’s that often it’s a good idea to start building very low level representation of the problem at hand (or very high level, direction doesn’t really matter, pick one that feels more natural) and then slowly work towards the other end of the spectrum (maybe start from other end at the same time too). Solution is then built from layers that slowly raise the abstraction level to the point where it’s natural to talk about the problem at hand. Be warned though, all the code shown in this post is quite rough and more of an sketch or notes for myself.

Nested lists of symbols sound like a good candidate for representing complex entities, so lets start there and define something that looks like a potion:

1

2

3

4

5

6

7

8

9

10

`(defn potionᵒ [item]`

`  ``(fresh [types]`

`         ``(firstᵒ types 'types)`

`         ``(memberᵒ 'potion types)`

`         ``(memberᵒ types item )))`

`=> (run 1 [q]`

`...     (potionᵒ q))`

`[(('types' 'potion' . <'_.0'>) . <'_.1'>)]`

So, a potion is a list, which contains a list, that starts with ‘types and has ‘potion in it. Those mysterious and just stand for anything that hasn’t been specified. In essence, list that I mentioned earlier can have more elements, but their content isn’t important for this goal.

Defining what item with flying effect looks like is almost similar:

1

2

3

4

5

6

7

8

9

10

`(defn effectᵒ [item effect]`

`  ``(fresh [effects]`

`         ``(firstᵒ effects 'effects)`

`         ``(memberᵒ effect effects)`

`         ``(memberᵒ effects item )))`

`=> (run 1 [q]`

`...     (effectᵒ q 'flying))`

`[(('effects' 'flying' . <'_.0'>) . <'_.1'>)]`

Where it gets a bit more interesting is when we define that we’re after an item that is potion and has flying effect:

1

2

3

4

5

`=> (run 1 [q]`

`...     (potionᵒ q)`

`...     (effectᵒ q 'flying))`

`[(('types' 'potion' . <'_.0'>) ('effects' 'flying' . <'_.1'>) . <'_.2'>)]`

Remember, that if we can define what something is (in essence, what relations does the primitive parts have), we have power over it and can reason about it: check if something is like what we defined, decide if something can be made to be this thing by filling in blanks and so on. This is the power of miniKanren and the reason I’m interested on representing traps, items and suchs as goals for high level AI routines. This is still very much work in progress and I haven’t nailed it down yet how to make the leap from reasoning about items and traps to reasoning how to use items to avoid traps.

I’m also wondering what are the chances that this type of system would result into some interesting emergent behaviour. Since it doesn’t directly encode what items to use in which situation, but rather what kinds actions and thus results are possible with given items, maybe it could find a solution overlooked by the designer? One still has to remember though, that miniKanren is “just” a dsl for specifying goals and a search engine that tries to locate solutions for the specified goals. It’s easy to get into inifinite recursion or end up with really slow routine.


___

#article 