---
title: III. Anyons
tags:
  - chapter
  - anyons
latex_header: \usepackage[style=apa, backend=biber]{biblatex}
latex_header_extra: \DeclareUnicodeCharacter{2212}{-}
transclude: "[[id:66aff1d3-bd45-45e5-9d31-d4292d76ae8e][FQHE/anyon
  chapter:Geometrical Phase]]"
id: 84c8fdf0-a17d-4610-b644-d298235f699e
mtime: 20220411171600 20211213124823 20211017163517 20211017163516
ctime: 20210528160149
---

# III. Anyons

# Intro

## New intro

- [ ] `Good line to introduce the chapter`

The main subject of discussion here will be a new class of (quasi-)particles:
anyons. In undergraduate courses, or, if you're lucky, highschool, we learn that two types of particles exist: fermions and bosons. These particles are distinguished by spin, half-integer and integer spin respectively. Anyons, as their name suggests, break this binary and are allowed _any_ type of spin,
creating a whole new category of particle.[^4] While anyons are fascinating in their own right, we are interested in them because, according to the canon explanation, anyons are two-dimensional particles. More suggestively, the space they occupy cannot be _approximately_ $2D$, such as a $3D$ space of $1nm$ height,
but _exactly_ two dimensional: a clear case of an infinite(simal) idealization. Of course, anyons would be just another plaything, were it not that, at the time of writing, anyons have rather strong empirical backing [@Bartolomei2020].

Another reason why anyons present such an interesting case, is that their explanation explicitly requires _topological_ arguments. Topological arguments, as I will show, show up in unexpected places and allow problematic idealizations to sneak in, as they smooth out many of the difficult to solve geometry. By tackling such an explicit use of topology in an infinite idealization, we will be able to use the argumentative structure in our general analysis of infinite idealizations. `The opposite of topology is geometry`

## What are we going to do

The following chapter will consist of four sections. In section 2, we will first attempt to understand what anyons are and why they are commonly thought of as a uniquely 2D phenomenon. The most important feature turns out to be how to define_path-uniqueness_, which is commonly defined either topologically or geometrically, the latter being the focus of section 3. To understand the topological notion of path-uniqueness (homotopy) we will examine how this works in 3D and then in 2D. Using a toy model we show that anyons are not a uniquely 2D phenomenon by constructing a non-simply connected 3D space using somewhat plausible assumptions.

After working through the problem topologically and gaining a thorough understanding of the conceptual difficulties that come with it, we turn our gaze to how path uniqueness is construed using the geometry of the space. One of the downside of the topological account is that it provides no way of calculating the specific phase of a particle, only stating that in 2D such phase could arise, so a geometric account would be welcome. It turns out that said geometry account (the so-called Berry-Phase) relies, unsurprisingly, heavily on the physical features of the system, making it difficult to reason about the possibily of a geometric explanation of anyons in the abstract. We therefore turn to a physical system which purportedly produces anyons: the Fractional Quantum Hall Effect (FQHE).

In section 4 we work through the FQHE, showing why anyons are involved and,
importantly, what idealization play a role in constructing the wave-function.
Before doing so, we recap how particles contained in magnetic fields `get`
quantized energylevels (Landau levels) and the basics of the simpler variant of the FQHE, the Integer Quantum Hall effect. These can be skipped by the impatient reader, as while some specifics of the IQHE carry over to the FQHE, mostly the conceptual basis is required, which is recapped at the end of section 3.XXX

Finally, we put all the pieces together in section 5, and see that while a geometric explanation _could_ be possible, it is not, at the moment, feasible. Later, in chapter `XXX`, I will argue if and why such a potential explanation should still be preferred to the topological account, but such conclusion cannot be drawn until we have gained a more thorough understanding of what a good explanation is in the first place.

# Topology and Anyons

In a standard physics undergraduate program, you learn that there are two types of particles, fermions and bosons, which are distinguished by their spin,
fermions coming in half-integer multiples $(\frac{1}{2}, \frac{3}{2} , ... )$
and bosons in integer multiples $(0, 1, 2, ...)$. A good starting question for understanding anyons would be: why _do_ we think there are only two types of particles? Why not $1$, or $3$, or infintely many? While many similar questions are as of yet unanswerable, such as why there appear to be only three generations of leptons (e.g. electrons, muons, tauons) or three fundamental forces in mhe standard model (electromagnetic, weak, and strong), this one does have an accepted answer. It is, as always, a combination of experimental results and theory. Fermions and bosons' share few features besides the fact that they are particles, but the important commonality is that they are both_indistinguishable_ particles. Every electron is the exact same as every other electron, and every photon is perfectly identical to the next. There is no way to tell whether two fermions or two bosons have switched places when you weren't looking. We will explore the consequences of this in more detail later, but the important consequence of this fact is that it induces an overdescription of the physical situation: we can mathematically describe two situations, one in which we have electron $1$ on the left and electron $2$ on the left. While mathematically distinct, these situations are physically identical, and in order for our physics to make sense we need to account for this distinction. The reasons for assuming indistinguishability could be a thesis topic in its own right, and the above description does not attempt to do it justice. The important point is _how_ we arrive from this indistinguishability to the fact that there are two types of particles: how does indistinguishability help us distinguish particles, and how do we mathematically distinguish these identical states?

As a warm-up, let us consider a rather handwavey argument. Handwavey, because it relies on the particles still being distinguishable, but it illustrates the point. Say we start with a system $\Psi_0$ of two particles, $x_1$ and $x_2$, each with their own probability distribution $\psi_i$$\Psi_0=\psi_a(x_1)\psi_b(x_2)$

Now, for our next trick, we will exchange the two particles, such that particle$x_1$ is in state $\psi_a$ and particle $x_2$ is in state $\psi_b$. If we suggestively take state $\psi_i$ to be mean something like "having probability $1$ of being found around $x=a$", then this exchange can be the physical exchange of the two particles. Now, of course, we do not know which particle is which, so writing down the 1-exchange wave function would be getting ahead of ourselves, but we do know that if we were to exchange the particles once again we should regain our initial wavefunction $\Psi_0$. To dentote this, we define an exchange operator $P$
which does just, and say that the wavefunction after exchanging twice (=
rotating by 360 degrees) is $\psi_{2\pi}=P^2\psi_0=1\psi_0$. To find the wavefunction of the 1-exchange system, we find

$\psi_{\pi}=P\psi_0=\sqrt{1}\psi_0=\pm 1\psi_0$

This yields two possibilities for particles: those for with $P=-1$ and those for which $P=1$. The latter are bosons and the former are fermions.[^7]

The above argument is too handwavey, so we would like to make it more concrete.
The way to define what we mean by "exchange/ability/". To start, the suggestively italicized _ability_ part of exchangeability hints at the fact that the _possible_ ways a particle _is able to be_ exchanged is of central importance.
One natural way of defining this is by looking at all the possible paths the particle can take. We would need to look at the _configuration space_ of the particles: the possible configurations of them and connections between these configurations.[^8] Now we need to supplant this with a notion of what it means for two paths to be _the same_, or, equivalently, what it means for two paths to be different. This idea of path-similarity depends on which factors we judge relevant when considering manipulating quantum particles, which we need to choose if we wish to obtain the most general description possible. Like most of physics, we would not want our description to depend on some sort of absolute position or orientation in space, so our description better ignore those. Beyond that, however, identifying the relevant factors of the space becomes more tricky. The two most promising candidates are a _geometric_ or _topological_ notion of path similarity. As it turns out, the latter is used in the most commonly accepted explanation of anyons, the main reason being the mathematical and conceptual simplicity it brings.

The main notion of similarity used to explain anyons, namely the topological notion of _homotopy equivalence_, roughly means that two paths are the same if they can be continuously deformed into one another. This differs wildly from_geometric_ path equivalence: there paths are only "the same" if they traverse the same path in the same space, they need to be `isomorphic`. Consider the difference between a mountain ridge versus a nice meadow. Geometrically, the two are very different, and if we were to care about how exhausting a hike over that distance would be we would certainly not neglect to take those differences into consideration. On the other hand, if we were an amateur nautical cartographer interested in plotting out all bodies of water in the area, we would consider both spaces identically topologically: neither of them has any lakes. It is clear why a topological approach to particle paths would be attractive, as it massively simplifies the set of possibilities down to the bare essentials. It is clear that sometimes we do need to consider the relevant geometry however: our hiker will no doubt complain if their map-making friend confuses meadows for mountains, or vice versa depending on their constitution.

Returning to anyons, we see that the approach taken for the _explanation_ turns out to be topological, while when actually calculating the phase we need to take into account the _geometry_. Here we will first discuss the topological argument,
after which we will consider the prequisites for and the geometrical argument itself in Section 3 and 4.

By focussing on the homotopy notion of equivalent paths, we release ourselves from the burden of having to examine each individual path and instead are able to focus on features of the _space_. Specifically, since we only need whether two paths are continuously deformed into one another, we just need to look at whether the space allows for such trickyness. This feature of a space is called its **connectedness**. A space is called **simply connected** iff all _loops_ can be deformed into a point, like in figure ref:fig:connectedness. For our purposes,
since we are looking at the position of a particle in spacetime, we can consider a space to be simply connected if it has no holes. Here a hole is a hole that
"pierces" the space: the handle in the "space" of a coffeecup and the hole in the "space" of a donut are prime examples, while the inside of a bottle or a bubble in a glass of coke do not count as "holes" for the sake of connectedness.
On the contrary, spaces with such holes are called _multiply-connected_, or sometimes more simply _non-simply-connected_ spaces.

This concept of connectedness allows us to understand the main assumption behind the handwavey argument above: we return to the same position after rotating 2 if the space is simply connected, because "being the same" means "being the same path" and "being the same path" means "being able to continuously deform them to each other" and "doing nothing" is the "point path" and you are only able to shrink all paths to a point in a simply connected space. This, of course, raises the question: is the configuration space of two identical particles always simply connected, i.e., why do should we return to the same system after rotating $2\pi$? As we will see, it is simply connected in $\mathbb{R}^3$, but _not_ in$\mathbb{R}^2$. This is why people say that anyons can only exist in 2D. As we will also see, however, is that this is not strictly true, as we can conceive of somewhat plausible multiply-connected 3D spaces.

### Phase

Much of the upcoming section will be centered around calculating the _phase_ of a quantum system, and it will be useful to briefly go over what we mean by phase and its relation to anyons. Briefly stated, the phase factor is a complex number which does not change the physical information if applied globally, that is when multiplying every wavefunction under consideration with it. The $\pm1$ applied by our operator $P$ is such a phase.

Phase arises because the empirical outcome of measuring a quantum state involves calculating the modulo-squared of the wavefunction. There are simply (at least)
two wavefunctions which arrive at the same outcome if you square them with their complex conjugate: - that wavefunction and plus that wavefunction. They are both perfectly fine mathematical representations of the same state, just like the fact that the square root of 9 can be both -3 and 3. When asked: what is the length of the side of a square field of 9 square meters, the answer is indeterminate: it can be either 3 or -3. Rather than saying it can only be positive, we can be a bit more general and say that the "phase factor" in front of the three is unphysical: it simply does not matter for calculating the surface area of the field what it is. We have, of course, some empirical preference for using positive lengths in stead of negative ones, but we do not such physical intuitions for wave functions, as they live in Hilbert Space and we unfortunately only have 4D spacetime to our disposal. Since wavefunctions live in _complex_ Hilbert space, the most general factor that would get $||^2$
away is not $\pm 1$, but $e^{i\theta}$, as that simply _is_ the square root of $1$ in$\mathbb{C}$. Thus any wavefunction will show empirical differences when multiplied with $e^{i\theta}\quad\forall\theta\in \mathbb{R}$

It is of course not immediately clear what this has to do with paths in configuration space or anyons for that fact. The answer is that, while systems could theoretically obtain any phase, they do not in general do so. We know from examining the time-dependent Schrodinger equation that it can be reduced to the time-_independent_ schrodinger equation times a phase factor, which depends on time and the energy of the system. However, while we said that phase does not matter physically, this is only the case for the system as a whole: if two systems have different phase they interfere. It's analogous measuring any other kind of wave: you will have to pick a starting point in order to describe the offset of a particular wave. These phases don't matter until you measure two waves interfering, which leads to inteference. For particles this leads to destructive interference for fermions: if the exact same wave would `xxxxxxxxxx`
then there is probability zero of it being there. This is the Pauli-exclusion principle.

Thus while phases do not appear to matter _prima faciae_, they are the reason matter is able to exist in the first place! Without the Pauli Exclusion Principle it would not be possible for matter to clump together, as everything would simply phase through each other (barring electromagnetic interactions).


## The configuration space explanation for anyons

The topological explanation gestured at above consists of roughly the following steps:

1) Construct the _configuration space_ of the system, that is, all possible positions our particle pair could be in.
2) Find all possible homotopy equivalent paths, and, by extension, the
   _fundamental group_ of the space.
3) Derive the 1D-representation of that group, that is, a scalar representing that group. This is the phase-factor.

We will go through these steps in detail for the case of anyons and other particles. After showing that anyons appear to only be possible in 2D, we construct a toy 3D-configuration space in which anyons are also possible.

### The 3D case

#### Constructing the configuration space

Our first task is to construct the configuration space for the exchange of $N$
identical particles in $3D$, after which we will examine its topological properties. The most general configuration space we can construct is one for
$N$ particles living in $d$ dimensions, which would be

$$
\mathbb{R}^d_1 \times \mathbb{R}^d_2 ... \times \mathbb{R}^d_N
$$

We shall for now focus on just two particles in $\mathbb{R}^3$, which would be the configuration space occupied by two $3$-dimensional vectors $(r_1, r_2)$ representing two particles$\mathbb{R}^3\times \mathbb{R}^3$
As we are dealing with identical particles, however, we need to add some extra structure, which results in our configuration space being much smaller than the above.

To simplify our notation and avoid having to conceptualize $9$-dimensional space, we can define our configuration space in terms of the center of mass of the particles $\mathbf{R}=\frac{(\mathbf{r_1+r_2})}{2}$ and their difference vector $\mathbf{r}=\mathbf{r_1-r_2}$. Clearly the configuration space of$(\mathbf{R}, \mathbf{r})$ is still $\mathbb{R}^3\times \mathbb{R}^3$. However, now we can pull a trick. We only care about exchanging the particles, right? It seems reasonable,
therefore, that the position of the system as a whole does not play in a role in determining all possible positions of the particle, e.g. it should not matter
(we assume, quite reasonably) whether we exchange two fermions in our lab on Earth or on Venus. For our purposes, then, we can safely ignore one of the two$\mathbb{R}^3$ s and simply focus on the relative distance and orientation of the two particles with each other.[^9] This simplifies the problem of finding the configuration space significantly.

Let us return to the constraints. The first constraint is the indistinguishability of the particles. Since it is impossible to distinguish the situation $(r_1,r_2)$ from $(r_2,r_1)$, we cannot take these two configurations to be separate points in configuration space and must remove them. We can represent this by "dividing out" the permutation group $S_2$ from our current configuration space,[^10] yielding $\frac{\mathbb{R}^3 }{S_2}$


#### If we view the configuration space not as separate particles but two coordinates of some system, CM & Distance, than the configuration space is much easier to visualize

#### Missing points are hard to justify usually begs the queston (maybe make an argument out of this.)

The second and final constraint is accounting for particles not being able to intersect with each other. The argument for _why_ we ought to, however, is rarely made precise. The general tendency, as expressed by `SOURCES`, tends to justifying the exclusion of these diagonal points by noting that this configuration space needs to account for fermions, which are subject to the Pauli-exclusion principle and thus cannot intersect. However, this argument presupposes the Pauli-exclusion principle and fermions as a distinct category of particles,
which precisely follow from this very argument! The justification clearly begs the question, but this does not appear to bother most. Some attempts have been made to provide a better justification, for instance using the de Broglie-Bohm pilot wave theory \[[@Brown1999]], but such interpretations have not found their way into the mainstream discussion on anyons. For now we shall follow the herd and accept the excision of the diagonal points from the configuration space, and shall return to such issues later.

Returning back to the configuration space, it appears we have no other choice than to excise the points representing the particles occupying the same space from our configuration space, denoted by $\Delta$. In the $(\mathbf{r_1, r_2})$
representation, $\Delta$ consists of the diagonal of points$\mathbf{r_1}=\mathbf{r_2}$, such as $(\mathbf{0}, \mathbf{0})$, $(\mathbf{1},
\mathbf{1})$ etc. In our current CM/distance representation, in which we only focus on the distance part $\frac{\mathbb{R}^3}{S_2}$, this amount to only excising single point at the origin, so $\Delta=\{\mathbf{0}\}$. Now we are finally able to write down the full configuration space $Q$

$$
Q=\mathbb{R}^d \times \frac{\mathbb{R}^d -\Delta}{S_2}
$$

of which we will only be studying the latter half $Q'$, e.g.

$$
Q'=\frac{\mathbb{R}^d - \{\mathbf{0}\}}{S_2}
$$

Finally we are able to make some clever remarks about the structure of the configuration space, starting (and ultimately ending) with its _connectedness_. As mentioned previously, as space is called _simply connected_
if, roughly, no holes pierce it. To placate the more mathematically oriented reader and be more precise, a space is called simply connected if
   it contains no non-trivial loops, meaning that all paths looping back
  around to itself (a loop) are _homotopy equivalent_ to a point, meaning that we are able to smoothly "close the loop" without it "snagging" behind a
   point somewhere. The "are able to" does a lot of work here: if there is
    even _a single_ way to contract the path to point we consider it possible to do so and therefore the _whole_ space simply-connected.

> [!example]
>

The difference of course, is that your rivals finger does not prevent _all_ paths to be contracted to a point, whereas the infinitely long cylinder does.

Returning back our example of two indistinguishable particles in three dimensions, we can visualize $Q'$ more easily if we restrict the distance between the particles by for instance setting$\mathbf{r}=|\mathbf{r_1}-\mathbf{r_2}|=1$ . The resulting space can be described in a number of different ways, and is called the _real projective plane_$RP^2$. You can visualize it as:

1) A sphere of radius 1 with all of its antipodal (points which oppose one another, like the North and South pole) identified (being taken as the same point).
2) The space of all possible lines of length 1 through the origin.
3) A hemisphere which behaves strangely at the boundary
4) A mobius band which also has its "sides" glued together in the same way a regular mobius band is constructed, namely by twisting it once.

20210610<sub>174954screenshot.png</sub>

20210610<sub>175017screenshot.png</sub>

In our "one-particle-at-the-origin" picture, we can roughly see the points in$RP2$ corresponding with one particle circling the other, with one crucial caveat: when we move particle 2 halfway around the other, performing in effect a
"half exchange," we return back to the same point, as the particles are indistinguishable from one another and we do not care about where their center of mass lies.

- [ ] Associate pictures with these paragrahs


- [ ] Give the loops better names than "half-exchange"

Now we finally, decisively determine the connectedness of this space. It turns out that there are two different possible loops around this "circle", loops again being paths that return to their starting position: one fully going around the "sphere" and one going halfway around it. This space is _not_
simply-connected, but not in a very complicated manner. The only path which is not "shrinkable" to a point is the halfway exchange path, because the only way for particle 2 to complete this loop is by "travelling" to the other side of particle 1. Even though the two points are the same, we can only connect them by traversing a distance of at least $2r$, therefore it is not collapsible to a point. Fortunately, our story ends there, as all other loops which start and return to the same position (in real space, not $RP^2$) _can_ be contracted:
imagine the loop of your shoelace closing.

We of course need to be mindful of the missing $\Delta=\{\textbf{0}\}$ and the fact that we are looking at the situation $d=|\mathbf{r_1}-\mathbf{r_2}|=1$ . Luckily these statements hold for any $d\in\mathbb{R}$. Even if $d$ is tiny, we will always be able to "lift" the loop over the missing point at the origin. Only $d=0$ would possibly provide some difficulties, but a point is contractible to a point, and$d=0$ is excluded from the space.

Therefore there are two different kinds of paths. Now we are truly able to appreciate how indistinguishabilty changes the number of "paths", as $\mathbb{R}^3-\Delta$ has only one kind of loop, namely the full exchange, which would lead to only one kind of particle existing.

- [ ] Add why this leads to particles, or at least a link to the section where we discuss this


- [ ] Add explanation of why RP2 is equivalent in the relevant respects to R3-delta/S2. This is not obvious for two reasons: Several layers of RP2  Q', because in Q' paths can move between the layers, and secondly because RP2 is not a sphere and Q' is not R3, so the embedding of the one in the other is not the same. Retractability is important here, see Munkers Ch 9.

#### 2D cannot be contracted to a piont because you cannot move over the missing points

Let us now turn to the actually interesting case of a $2D$ system and how it gives rise to different homotopy equivalent paths. We start off with our CM/distance representation, but this time in 2D, leading to our full configuration space

$$
Q_2=\mathbb{R}^2\times \frac{\mathbb{R}^2 -\Delta}{S_2}
$$

and will be focusing on the latter half,

$$
Q_2'=\frac{\mathbb{R}^2-\Delta}{S_2}
$$

where once again, $\Delta$ is the set of points where $(\mathbf{r_1},\mathbf{r_2})$ intersect, i.e. the set $\{\mathbf{0}\}$, and $\frac{}{S_2}$ indicates the equivocation off all configurations symmetric under permutation invariance, i.e. $(\mathbf{r_1, r_2})=(\mathbf{r_2,r_1}) \quad \forall \mathbf{r_1,r_2}$.

If we once again, for ease of visualization, restrict $Q_2'$ to only those configuration for which $|\mathbf{r_1-r_2}|=d$,picking $d=1$ for convenience, we obtain the space commonly referred to as the _real projective line_ $RP^1$. Unlike its planar cousin from before, $RP^1$ allows us to make some simpler arguments regarding its connectedness, as it is [[Homeomorphic|homeomorphic]] ("topologically equivalent")
to a circle in $\mathbb{R}^2$, and since the circle is multiply-connected with However,
just because it is homeomorphic does not mean they are "the same space", as$RP^1$ can equivalently be described as

1) The set of all lines crossing the origin in $\mathbb{R}^2$
2) A circle with each opposite point identified
3) The real line with a "point at infinity", which would be a single point "at" $-\infty$ and $\infty$.

As with $RP^2$, we consider the 1-exchange and 2-exchange paths. Clearly the 1-exchange path is non-contractible again, for the same reasons as before.
However, unlike $RP^2$ or the sphere, a 2-exchange in $RP^2$ or the circle is_also_ not contractible to a point. This is relatively obvious for a circle, as the path of the particle is contrained to the actual circle, but it easy to see that the same would hold in our actual configuration space $Q_2'$: a missing point in $R_2$ _does_ consitute a hole, as it "pierces" the space. Therefore any loop encircling our missing point $\Delta$ cannot be shrunk to a point, since there is no way to "lift" it over the hole, similar to how an infinitely long cylinder would act in $\mathbb{R}^3$. Therefore we have at least three equivalence classes of homotopy-equivalent paths: no exchange, 1-exchange, _and_ 2-exchange.

That is not all however. Since a 2-exchange differs from a point, we can simply add another exchange (4-exchange in our lingo) to create a new loop which is_also_ not homotopy equivalent to a either a point nor a 2-exchange. Moreover, it matters which way we go about exchanging these particles: a clockwise loop and an anti-clockwise loop cannot be smoothly deformed into one another, as the path would have to cross the origin. Therefore we apparently have the same number of possible paths as there are integers\![^11] A bit of a step up from the situation in $3D$: instead of just two types of particles we suddenly have a
(countable) infinity of them! As we shall see, this will lead to the anyons being able to take on "any" phase.

- [ ] also add why Q<sub>2</sub>' is isomorphic to RP1.

#### P Another way of arguing for the same thing is by using the defintiont that phase is the 1D rep of the fundamental group of the spaceh

While categorizing configuration spaces is all very well and good, it is high time to connect this back to the physics, as we have not yet shown how the equivalence classes of homotopy equivalent paths relate to the number of particles. The way to do so is to extend our collection of equivalence classes slightly and describe what is called the _fundamental group_ of a space. The fundamental group $\pi_1$, also called the _first homotopy group_, of a space is, as the name suggests, a _group_ consisting of the set of equivalence classes of homotopy equivalent paths and path-concatenation as the group action.[^12]
Path concatenation is what it sounds like: in the fundamental group of $RP^2$ we have two homotopy classes of paths, the 1-exchange and the 2-exchange.
Concatenating these paths is simply traversing the one after the other,
resulting in a "3"-exchange, which is the same as a 1-exchange and in our group.[^13]

We already obtained the fundamental groups, which roughly look like

$$
\pi_1(Q_3')=\{X_0, X_1 \cdot\}
$$

for the $3D$ case with $X_1$ being the single exchange, $X_0$ doing nothing (and the double exchange), and $\cdot$ being path-concatenation and

$$
\pi_1(Q_2')=\{X_0, X_1, X_{-1}, X_2, X_{-2}, ... \cdot \}
$$

for the $2D$ case with $X_0$ being doing nothing, $X_i$ a clockwise $i$-exchange, and $X_{-i}$ a counterclockwise $i$-exchange.

Fantastic, so we are done, right? Well, yes, sort of, however the point of writing down these groups in addition to simply finding the homotopy classes is that hopefully we are able to do slightly more with the former. While that could be possible with these groups, it might be nicer to relate them to some more thoroughly classified groups in order to save ourselves some work. Additionally,
the groups we found are those for $2$ particles, and being able to easily generalize these groups to any $N$ number of particles. Rigorously deriving these fundamental group of a space is not trivial, the standard references for the fundamental spaces being \[[@Fox1962]] and \[cite//b:@Fadell1962]. Insead of doing this rigorously like mathematicans, we will go about this as physicists: look at the result and then convince ourselves they make sense.

This relating is done through finding an isomorphism between these groups. It turns out that, for $N$ particles, the fundamental groups are

$$
\pi_1(Q_3')&=S_N \\
    \pi_1(Q_2')&=B_N
$$

##### TODO Symmetry group

Here $S_N$ is the _symmetry group_, the set of all unique permutations of $N$ "things", together with the permutation operation $P_i$, which you could define as exchanging thing $i$ with thing $i+1$.

> [!example]
>

##### Braid group

The fundamental group of our $2D$ configuration space is isomorphic to the
_Braid group_, a group often studied in knot theory as braids can be seen as cut knots. The $N$-dimensional Braid group can be seen as all the possible
_braids_ of $N$ strands, together with the _braiding composition_ $R_i$ and its inverse $R_i^{-1}$, which stand for exchanging braid $i$ and $i+1$
clockwise and counterclockwise respectively. A braid is a set of strands
     crossing over and under each other and fixed at either end. Specifically,
     two braids are the same if the strands can be moved into the same
     configuration without phasing through each other or moving the endpoints.
     Because of this, the Braid group fundamentally differs from the symmetry
     group, as fr the symmetry group $\{123\}$ and $\{231\}$ are the same, they are different elements in the Braid group, see ref:fig:braidvssymmetry

- [ ] add figures that show off the difference between braid group and symmetry group


- [ ] Add some interesting properties

1) Every braid group has infinite elements, because $R_i^n\neq R_i$.
2) Braids cannot "move" back

The Braid group can help us in two ways: it can show us which phase anyons pick up and provide us with some physical intuition.

The phase of a system under exchange `is defined as` the 1D representation of the fundamental group

#### We can use some intuition about the braid group and braids to construct a somewhat reasonable 3D space which is also multiply connected.

The braid group also allows us to use some physical intuition to this otherwise rather abstract discussion. This will allow us to construct a different _three_-dimensional configuration space which can still give rise to anyons.

By taking the $y$-axis to represent time and the $x$-axis the 2D plane the particles move in, we can imagine the _braids_ of the braid group to be the_worldlines_ of our anyons. While this representation is not entirely accurate
(the braid-group is technically only the group of the homotopic paths of the distances with two particles), if we take it to correspond approximately we see why these braids `do not work` in $3+1D$ : =braids can untangle themselves in 4 dimensions. However, this is only the case for 1D braids, if instead they are thicker, then they can get entangled.

- [ ] Give more acceptable physical intuition

[[If particles cannot be closer than the thickness of the strip, the configuration space is approximately 2D]]

#### TODO Asides: we are now working in projective space, which is very weird. We need to check whether QM still holds

#### TODO Aside: kets stand to states as (universal) covers stand to normal spaces

# Geometric phase?

The explanation of the previous section has left us with a bittersweet feeling.
We made some good arguments for the existence of an entirely new class of
(pseudo-)particles! Think of all the new physics we could do: quantum computers,.... that's about it, but nonetheless very exciting! However, it came at a rather severe cost: us accepting a problematic idealization, blech! Is there then no other option? No one to save us? Are we doomed to accept platonism? No, luckily we need not stoop so low.

Even if we accept the 2D idealization, the previous section still left us a little unsatisfied. It provided us with an explanation of the _possibility_ of anyons, but crucially not with the tools to know _what_ phase we should expect from any potential anyon. According to ref:eq:anyonphase, anyons take on an exchange-phase that's a multiple of the number exchanges and which depends on the direction the exchange took place, but not much else. It could be any multiple of the winding-number, which does not provide us with much predictive power if we ever want to perform an experiment looking for these buggers. "But",
I hear you say, "did \[[@Bartolomei2020]] not definitively show that anyons exist?" We'll get there when we get there, _Jeremy_, but we can ask some annoying questions to get us started.

Would they simply perform some experiment, somehow measure the phase and see that it is different: would this be convincing enough evidence? No, of course not, we would want to predict the phase beforehand and see how well we measure up to Mother Nature. Furthermore, how did they know where to look? Presumably something 2D-y, but that can be a lot of things: graphene is not very interesting on its own.

Before spoiling the surprise about what the experimental setup is, let us step back once again and wonder for a bit: how could the phase change if not for this abstract topological gegrabbel? To make an educated guess, recall the end of the last section, where we learned that the wavefunction plus phase _projects down_ to$|\Psi|^2$, which is the physically relevant quantity. So we have a vector in Hilbert space, $\ket{\Psi}$, which varies in some way which does not effect its length $|\Psi|^2$. Of course, one of the "things" varying is the phase, but the phase does not simply change randomly on its own with everything else staying the same, that would violate Schrodinger's equation.

Everything in the Hamiltonian can act as a parameter we can vary which could potentially impact the phase, the most obvious being the time $t$. It turns out that $t$ does indeed lead to a phase, the so called dynamical phase$e^{iEt}$. However, this unlikely to be the phase we are looking for, as it varies rather quickly and all systems are subject to this phase, no matter if they are exchanged.

- [ ] Improve description of why the dynamical phase is not it

What then? The most straightforward seems to be the position, as that is explicitly what is varied during exchange. However, it is not immediately obvious why this would lead to a change in phase in a way that is different from the topological explanation given before, which is not an improvement: no calculation. Have I led you to a dead end? Was it all a ruse?

Fortunately for us I have brought an excellent analogy to this phase-picnic. The answer has to do something with geometry of course, as was spoiled in the introduction to this chapter, and we are so blessed that there is even a complete mathematical field examining moving things over geometry: differential geometry, same thing being used to do gravity and such.

- [ ] Absolutely horrendous intro.

A good analogy to the phase of a vector in Hilbert space would also have something like a vector varying which would affect something else than its length and position (as that is what we possibly would like to vary, and that would hardly be surprising). Again, lucky bastards we are, there exists an_extremely_ straightforward analogy. A situation in which a vector is moved, its length is unnaffected, but then suddenly after moving it in a circle something is changed: the angle of a vector in regular ol' $\mathbb{R}^n$. A vector in a real vector space does not have much to vary in addition to its position and length,
the only thing left is its angle!

When we transport a vector along some curved surface its angle changes. Hardly surprising, as there are a lot of ways to transfer something, but slightly surprising if we only think of transporting as transposition:

       ^                    ^
      /                    /
     /         --\>        /
    /                    /

does not change the angle one bit! How then? Well, we said _along_ a _surface_, just moving it in $\mathbb{R}^n$ is cheating a bit eh. Moving along a surface is done with_parallel transport_, which means, as you smart cookies guessed, means keeping it parallel to the surface of said... surface. When we do this something surprising does happen: when we complete a loop on a surface with some _curves_, such as the sphere, that is not a circle or a straight line we end up at a different angle than we started! WHAT!

## How does geometrical phase get there

As Berry said in his original paper, the occurence of the geometrical phase does indeed appear quite "magical" [@Berry1984]. However, as [@Simon1983]
soon thereafter elucidated, the mystery largely disappears we link it to a more general geometric property: [[Holonomy|Holonomy.]]

Holonomy is the phenomenon of a vector (or more generally any mathematical object) not remaining completely invariant after being [[Parallel transport]]ed along some curved surface. An example is in order.

### North pole example

Say you are at the North-pole, looking "south" (every direction is south) along the Greenwhich meridian line. Your field of vision (let's just take the center of it for simplicity) is our vector which we will be parallel transporting. It has a length of approximately 5km (this does not really matter) and is facing wherever you are looking, originating wherever you are standing. We will now only change one of these variables gradually, your position. You start to bravely swim along this meridian, eventually reaching the equator. Since you are already making a fool's journey, you figure you might as well lean into it and add an extra condition: you will never turn during your journey. Meaning that once you reach the equator, instead of turning 90 degrees to face East, you shuffle Eastword across Africa like some sort of stray crab. Once you reach the international date line in the Pacific ocean, you do not stop acting the fool and begin imitating the jellyfish you meet there, swimming backwards on your back in a straight line back to your starting point.

Once you have been certain you returned back to the same spot again, the question now is: which direction are you facing? Given that you never turned around, you might have expected to face England once again. However, to your utter dismay you are still staring down that boring international date line,
ocean as far you could see. Despite never turning around, you have ended up turning $180^\circ$ nonetheless! Curse you, geometry!

This extra angle that you picked up on your Oddyssey is a/has something to do with **holonomy**, which is a fancy word for the failure of parallel transport along a certain manifold, in this case the 2-Sphere (in normal people talk: the surface of a sphere). While this may be shocking to our foolhardy protagonist,
there is something deeply intuitive about not ending up facing the same direction here. But being intuitive does not mean easy to explain: all we know for now that this has something to do with the curvature of the space we are traversing, but not exactly which value it obtains .[^4]

> [!comment] 
> These two questions and answers are rather handy, and they cite the following two papers as useful
> https://physics.stackexchange.com/questions/383281/when-is-the-berry-phase-only-dependent-on-path-topology
>
> https://physics.stackexchange.com/questions/235503/why-is-the-phase-picked-up-during-identical-particle-exchange-a-topological-inva?rq=1
>
[cite:@Leinaas1977]
[cite:@Knapp2016]


## section

Turns out this also works in QM! The berry phase does this for us. So great,
let's just calculate the Berry phase right? Well, sure, but we cannot just calculate the Berry phase without a Hamiltonian, wavefunction, all that good quantum stuff, for that we need some context.

Turns out we have one very promising candidate: the fractional quantum hall effect. To not waste time, let's calculate it:

$$
e^{i\theta}=\exp{-i\oint_C \mathcal{A}_i(\lambda) d\lambda^i}
$$

where $C$ is the path traversed by the particle through some parameter space, $\lambda^i$ the parameter being varied and $\mathcal{A}_i$ the _[[Berry Connection]]_ for a specific quantum state $\ket{n(R)}$, defined as

$$
\mathcal{A}=i\bra{n(R)}\nabla_R\ket{n(R)}
$$

- [ ] clean up lambdas and Rs

We have finally reached the point at which we have no choice but to look at an actual physical system, as we need to have an actual wavefunction to measure things by. The system that has historically been ascribed anyons is called the_Fractional Quantum Hall Effect_, which is also the subject of the recent experimental results by \[[@Bartolomei2020]]. Evaluating the merits of the geometrical approach to anyonic phase, then, necessitates a clearer understanding of the FQHE.

# The Quantum Hall Effect

- [ ] Put this somewhere else, preferably at the end


- Following \[[@Norton2012]], we know how to interpret this: we can demote an idealization to an approximation if we are able to show that there is a
    smooth limit.
- This is exactly the problem, according to \[[@Shech2019]:] the topological explanation of anyons requires an _exact_ 2D system (or a rather ad-hoc 2D system as we saw).
- Therefore we cannot call this approximately 2D.
- According to \[[@Shech2019]], this is a problem for those with nominalist inclinations[^1], as the instantiation of abstract mathematical structures in the real world would be an issue.

  - Such an argument can only be made, however, through the use of the EIA which was discussed in the previous (or next?) chapter.
- Therefore, it would do such people well to examine the physical effect thoroughly for any signs of this.

In this chapter, we will examine the inner working of the Quantum Hall Effect. This is needed in order to understand the following

1) Why do people say that these particles are anyons
2) What idealizations are made in the explanation of the quantum hall effect separate from the topological one.
3) To calculate the Berry phase

Readers less interested in the details can skip to the last subsection of this section `link` and the next section `link`.

- [ ] justify this slightly better

The Quantum Hall Effect is the quantum version of the classical hall effect, a rather straightforward consequence of moving charged particles in a magnetic field. It was discovered all the way back in `XXXX` by Edwin Hall, who claimed it a novelty which would never have any use-case.

- [ ] Source

Today Hall-Effect sensors are widely used to pick up magnetic fields and rotations of conducting materials. More esoteric applications are as potential long-term space-travel propellants in so-called Hall-Effect thrusters, which are a specific form of ion propolsion, which can generate a low thrust for a very long amount of time.

- [ ] Put this in words, not bullet points

The basics of the effect are rather simple

- Strip which has current flowing through it.
- Magnetic field perpendicular to that strip
- Induces Lorentz force which pushes particles to one side, increasing their concentration and creating a potential difference, inducing a voltage changing the resistivity.
- This resistivity linearly depends on the voltage, which linearly depends on the concentration difference which linearly depends on the strength of
     the magnetic field, thus yielding a linear dependence of the resistivity
    to the strenght of the perpendicular magnetic field.
- Looks like figure ref:fig:che

However, as most classical effects, they only hold in a certain regime. When we clean up the materials, lower the temperature dramatically (<2K) and increase the magnetic field strength considerably, we observe the _Quantum Hall Effect_
(QHE): rather than a linear dependence on the magnetic field strength, the resistivity shows these strange plateaux at rather consistent values, as inref:fig:qhe. The spacing between these plateaux does not seem to differ between different materials, which is even more curious.

So: why? Why do we see these plateaux, and why at these levels? The short answer (partially) is: the impurities in the sample lift the degeneracy of the
eigenstates of the Quantum Hall system, called Landau levels, and _localizes_
some of those states, rather than the states extending from one edge of the
sample to the other (akin to the wavefunctions of a particle in a box). These
localized states do not conduct current (as do not span the system, and
resistivity is measured from end to end), thus leading to the plateaux in the
resistivity: we change plateaux when all the localized states are filled and we
move to different extended states. The specific values of these levels depend
on weird physics at the boundaries of the system called _edge-modes_, but in short the levels correspond to the number of filled Landau levels: at higher
magnetic field strengths the levels can accommodate more states, thus the lower
the magnetic field strength the larger the number of available levels, leading
to a smooth-looking linear dependence in the classical regime.

There are quite some caveats to the above story, but that is the gist of why the effect happens for _integer levels_. The less interested reader can skip over the following section describing the corresponding _Integer Quantum Hall Effect_
(IQHE) and head to the description of its fractional cousin, where the same does not hold. Specifically, the IQHE requires one massive idealization: electron interaction is neglected completely. As we shall see, this idealization cannot hold in the FQHE.

## The Integer Quantum Hall Effect

In order to do as little physics as is possibly required, I will skip most of the justification for the quantum formalism of the QHE (quantizing the classical Hamiltonian, finding the commutators) and many of the intermediate steps to arrive at the relevant results. I point the interested reader to
\[[@Tong2016]\[\[]]] for a quite accessible and to \[cite//b:@Arovas2020] for a more thorough pedagogical discussion of these issues, and to
\[[@Stone1992]],Prange1987,Doucot2005 for rather complete, less pedagogical sources.

As mentioned previously, the Integer Quantum Hall Effect (IQHE) is the observation of plateaux in the Hall resistivity $\rho_{xy}$ at regular intervals. These intervals happen to be integer multiples of the _quantum of resistance_  $R_q=\frac{2\pi\hbar}{e^2}$. `check whether this is so`

- This is rather curious, why so precise?
- In fact, so precise that these experiments are used to determine the quantum of resistance.
- Why are they there, and why at those levels?

As physicists, the first thought as to the origin of these plateaux probably goes to the energy eigenstates of the system, which turns out to be correct! The plateaux correspond to the general energy eigenstates of a system of charged particles moving in a perpendicular magnetic field, so called Landau levels.

- It will be difficult to properly understand the QHE without first briefly going over landau levels.

`Assumptions`

### Landau Levels

Here we already start to sneak in our idealizations: we will treat this system as if it is two dimensional. `However, this system can be easily extended to 3D, see XXXX`

The simplest Hamiltonian for a system of particles moving in a magnetic field is

$$
H=\frac{1}{2} m(\hat{\mathbf{p}} +e \hat{\mathbf{A}} )^2
$$

The  magnetic field is perpendicular to the $x,y$-plane, so we define the vector potential $\hat{\mathbf{A}}$ using our knowledge that the magnetic field is perpendicular to the plane $\nabla\times\hat{\mathbf{A}}=B \hat{z}$, to be

$$
\hat{\mathbf{A}}=\begin{pmatrix}
0\\
xB\\
0
\end{pmatrix}
$$

`This will be appendix` The easiest way to find the energy eigenstates is the way all Hamiltonians get solved: treat is as the harmonic oscillator. As the Hamiltonian of the "normal" harmonic oscillator is

..


These allow us to define raising and lowering operators`At this point we introduce new variables. These are raising and lowering operators, entirely analogous to those that we use in the harmonic oscillator. They are defined by`$a= \frac{1}{\sqrt{2e\hbar B}} (\pi_x - i\pi_y) \quad a^\dagger = 1\frac{1}{\sqrt{2e\hbar B}} (\pi_x + i\pi_y)$

The commutation relations for $\pi$ then tell us that $a$ and $a^\dagger$ obey$$
[a, a^\dagger] = 1
$$

$H= \frac{1}{2}m \pi^2   = \omega_B \left( a^\dagger a + \frac{1}{2}  \right)$
We find that the energy eigenlevels are$\ket{n}=\omega_B\left(n+\frac{1}{2}\right)$

### Calculating the degeneracy

We started by saying that the plateaux in the IQHE correspond to the various filled Landau levels of the simple particle in a magnetic field system. We still need to prove this, namely by deriving the conductivity for the Hall states.
This can get rather messy, so I will show put the derivation for a single particle here, and the more general derivation of the so called _Kubo formula_ in the Appendix.


To find the resistivity, we use Ohm's law, which relates the energy of a particle to the current density (current over area)

$$
\mathbf{E}=\sigma \mathbf{J}
$$

Our mechanical momentum is$\hat{\mathbf{\pi}}=\hat{\mathbf{p}}+e \hat{\mathbf{A}} = m \hat{\mathbf{\dot{x}}}$
Classically, the current (for a single particle) is simply $\mathbf{I}=-e\mathbf{\dot{x}}$, but isnce we are working quantum mechanically we take the expectation value

$I=-e/m \sum_filled_states \bra{\psi}-i\hbar\nabla+e \hat{\mathbf{A}}\ket{\psi}$

We are working in Landau gauge.

...

We end up with


### Edge modes

In order to provide a more thorough calculation (i.e. not just considering a single electron) we take advantage of a the fact that the system is bounded. I will not reproduce this here.

### Robutsness

The explanation above shows us why there are plateaux at the levels we see, and even gives us a hint as to why those states would be rather
 stable, but it has not yet told us _why_ these plateaux persist over a range of values yet, just that something is going on at those values. We
 have only shown that at complete filled Landau levels ($\nu\in \mathbb{N}$) the longitudinal resistivity $\rho_{xx}=0$ and that the transversal resistivity
$\rho_{xy}$ is an integer multiple of the quantum of resistance. However,
if we were to move even slightly away from the completely filled Landau
 state where $B=\frac{ne}{2\pi\hbar}\frac{1}{\nu}$, all our previous arguments hold no water and there is no reason to expect anything already covered
to hold.

This is obviously a problem, as an effect which only shows up at a specific real number would never be experimentally observable. We will need do some
dirty work in order for `this` to make sense. In fact, the solution not only requires some dirty work: the solution _is_ dirtiness.

Experimental samples are inherently dirty (here meaning: containing other elements than the intended sample[^5]), and these impurities require us to re-examine our previous claims somewhat[^6]. These impurities lead to two vital insights which will allow us to solve our puzzle:

1) They (unsurprisingly) break the degeneracy of the Landau levels, resulting in more swept out states as in ref:fig:disorder
2) They (more surprisingly) turn many _extended_ quantum states into _localized_ ones.

![](../media/broadlandau.png "Density of states in the IQHE with and without disorder")

![](../media/breakdegen.png "Extended to localized states")

This might sound all well and good, but certainly there is a limit to the amount of disorder we are allowed to introduce into our system? Surely the spokes of my bicycle should not be able to serve as Quantum Hall systems.

Correct you are: in general we demand that a) the strength of the disorder
(which we model as a random potential) ought to be small relative to the Landau level splitting and b) the disorder does not dramatically vary on small scales,
such that for a particle influenced by it the potential can locally be seen as constant. We can express these as

$$
V_{disorder}<<\hbar\omega_B
$$

and

$$
|\Delta V|<<\frac{\hbar \omega_B}{l_B}
$$

where $l_B$ is the magnetic length, `roughly the length scale at which these effects are relevant`

{/*Now consider what this means in a random potential with various peaks and troughs. We’ve drawn some contour lines of such a potential in the left-hand figure, with + denoting the local maxima of the potential and − denoting the local minima. The particles move anti-clockwise around the maxima and clockwise around the minima. In both cases, the particles are trapped close to the extrema. They can’t move throughout the sample. In fact, equipotentials which stretch from one side of a sample to another are relatively rare. One place that they’re guaranteed to exist is on the edge of the sample.



The upshot of this is that the states at the far edge of a band — either of high or low energy — are localised. Only the states close to the centre of the band will be extended. This means that the density of states looks schematically something like the right-hand figure=. 



Conductivity Revisited For conductivity, the distinction between localised and extended states is an important one. /Only the extended states can transport charge from one side of the sample to the other. So only these states can contribute to the conductivity./ Let’s now see what kind of behaviour we expect for the conductivity. Suppose that we’ve filled all the extended states in a given Landau level and consider what happens as we decrease B with fixed n. Each Landau level can accommodate fewer electrons.



But, rather than jumping up to the next Landau level, we now begin to populate the localised states. Since these states can’t contribute to the current, the conductivity doesn’t change. This leads to exactly the kind of plateaux that are observed, with constant conductivities over a range of magnetic field. So the presence of disorder explains the presence of plateaux. But now we have to revisit our original argument of why the resistivities take the specific quantised values (2.3). These were computed assuming that all states in the Landau level contribute to the current. Now we know that many of these states are localised by impurities and don’t transport charge. Surely we expect the value of the resistivity to be different. Right? Well, no. Remarkably, current carried by the extended states increases to compensate for the lack of current transported by localised states. This ensures that the resistivity remains quantised as (2.3) despite the presence of disorder. */}



I will leave the more detailed explanation for why the extended states compensate for the localized states for the interested reader, see text [@Tong2016]

That is it for the IQHE, as we derived the two things we needed from it: we gained a general understanding of why the plateaux have their values (they are the energy eigenvalues of the Landau levels) and, more importantly, we roughly understand why these plateaux are robust. Unfortunately, this is not the end of the story, we did not even mention anything topological yet! For that we finally turn to the Fractional Quantum Hall Effect.

## The Fractional Quantum Hall Effect

Following the naming convention of the IQHE, the Fractional Quantum Hall Effect
(FQHE) refers to the observation of plateaux at _fractional_ values of the quantum of resistance in the Hall resistivity $\rho_{xy}$. Sadly, very few of the arguments mentioned above will be able to explain these plateaux, as we have only shown that they appear at fully filled Landau levels. However, our intuition about the robustness will still hold.

The goal of this expos\\'e is twofold. First we want to gain a general understanding of how the FQHE is thought about in general: what assumptions go into calculating the relevant parameters, which idealizations are noteworthy,
etc. The other main goal is the 'derivation' of the Laughlin wavefunction, the wavefunction used to describe the FQH system, and its excitations. At the end we will arrive at the problem of calculating the exchange statistics of these excitations, which turn out to be _anyons_, but not actually compute them yet:
this will be done in section ref:sec:GeometricPhase.

The key difference between the description of the Fractional as opposed to the Integer Quantum Hall effect is the inclusion of electron interactions in the former, which becomes impossible to ignore at the energy scales above $\nu=1$,
which is where most of the FQHE physics is done. As a result the reasoning cannot be as rigorous as before. In the IQHE we could pretend that all the states occupied the same Landau level, which allowed us to calculate the wavefunctions and energy levels, leading to the derivation of the Hall resistivity and confirm our suspicion that the plateaux correspond to fully filled Landau levels. Only after doing that did we let go of that idealization and allow the degeneracy to be lifted in order to argue that the plateaux were robust.

This order of operation is no longer possible in the FQHE, as the electron interactions lift the degeneracy of the Landau levels from the start, forcing us to compute the wavefunctions in a different way. A first approach would be to use perturbation theory: model the electron interaction as a small perturbation to ref:eq:landauham and then gradually compute a better and better approximation to the actual wavefunction. While this is fine for simple two-electron systems,
the number of electrons in a QH system is closer to $10^{23}$. That is a rather large matrix to diagonalize, not even close to possible to do numerically.
Therefore, we need to pull some tricks.

The trick is: do not compute the wave function, just write one down. That is exactly what text [@Laughlin1983] did, yielding what we now call the **Laughlin wavefunction**

[[The Laughlin Wavefunction]]

Laughlin of course did not just simply write down a bunch of wavefunction and pick the one he liked best, it is motivated by some observations from the system and from some general conditions we have to place on any wavefunction.
Specifically, in a previous paper [@Laughlin1983a] he derived the wavefunctions for three particles in the FQHE. Recapping this in the case of two electrons is worthwhile.

We have a system of two electrons with a potential $V(|r_1-r_2|)$.

- To solve such systems, it's easiest to work with angular momentum.
- If we want to work with angular momentum, the gauge we picked before (Landau Gauge) is not very useful, as it does not include any kind of rotation

  - Instead we pick _symmetric gauge_, which is $\hat{\mathbf{A}}=-\frac{1}{2}\hat{\mathbf{r}}\times \mathbf{B}= -yB/2 \hat{\mathbf{x}} + xB/2 \hat{\mathbf{y}}$
- Skipping multiple steps ahead, we see that the wavefunctions look like

       ψ ∼ (z1 + z2)M (z1 − z2)me−(|z1|2+|z2|2)/4l2 B
 

Unfortunately this does not uniquely or straightforwardly generalize to N particles, so we have to pull a few more tricks.

1) We do try to generalize, and say that a wavefunction for N particles will look something like $f(z)e^{something}$
2) We _insist_ that the wavefunction be in the Lowest Landau Level (LLL) it can possibly be: there are no other Landau levels it can fall back on.
         This is rather strong. This leads to the claim that $f(z)$ _must_ be analytic. `how`
3) Since the state will have to describe fermions, the wave function must be anti-symmetric under exchange of the particles, which requires $f(z)$ to be odd.
4) Finally, since we need to conserve angular momentum, we require that `f(z) be a homogeneous polynomial of degree M, where M is the total angular momentum.`

All these constraints add up to the fact that $f(z)=\prod_{j<k}(z_j-z_k)^m$, with $m$ odd.**This is what people mean when they say that the LWF falls into the same universality class as the actual wavefunction, as any wavefunction needs to account for this.[^3]**

Well, neat, you might say, but this still just describes fermions, I thought we were going to be talking about anyons! Right you are, things only really get exciting once we start talking about _excitations_ of this ground state.

{*/ I generate the elementary excitations of g by piercing the fluid at z, with an infinitely thin solenoid and passing through it a flux quantum t) cp =- hc/e adiabatically. The effect of this operation on the single-body wave functions is (z-z, ) exp(-4lzl')-(z-z, ) "exp(--'. ~z~'). (») Let us take as approximate representations of these excited states (13) '4 "=&.,''4"(--'Xl, (, l')In(, ——". I(n,.(*, —, )"),*/}

- The excitations of the FQH state (technically of the state described by the Laughlin wavefunction, which are not exactly alike)

# Geometric Phase

## The Cone Example and Holonomy

Parallel transport is a bit strange. On a flat Euclidean plane, nothing happens.
A cone is like a flat Euclidean plane glued together in a weird way, like this

- ![](../media/conefold.png)

Where side $s$ is glued to side $?$ in order to yield a smooth surface, with the exception of the problematic point $S$.

We can then calculate our parallel transport by simply "doing" the parallel transport on the surface of the "flat" cone.

The vector is transport from the one side to the other, eventually reaching the edge $s$, from where it is suddenly teleported to $s$, ending up with a much different angle.

- ![](../media/transport.jpeg)

https://www.physicsforums.com/threads/parallel-transport-and-cone.1000209/

This angle difference is directly related to the angle of the cone. We see that the sharper the cone, the bigger the failure of parallel transport (holonomy) will be.

The strange thing is, of course, that this angle difference appears rather suddenly only after we completed >1 round. However, were we to move an 'actual' vector on a cone, we'd expect this to happen slowly, right? We want to get rid of the "discontinuous jump".

This question proves rather difficult to answer, for two reasons.

1) The holonomic angle is only defined when the vector returns to its original position, we don't expect thing to be the same when we simply stop the transport somewhere in the middle.
2) Actual cones are not this pointy.

{*/http://applet-magic.com/paralleltransport.htm */}


In actuality, when you deform the cone in the figure above, the angle _does_
change continuously along the path of the cone wrt beginning angle, but that's
very often the case and does not count.

Instead of having the continuous parameter be the angle of the cone, a better one would be the "path", since we are interested in paths after all. Here we
see that if we take any path that does not cross the "seam", the angle
remains 0. But the seam is kind of arbitrary, so that is not really fair. We do
know, however, that if the path encircles the tip of the cone it definitely
passes the seam. So now we have our discontinuity: all paths that do not cross
the tip do not gain a holomorphic angle (because those paths are the same as
paths in Euclidean spacetime), while as soon as the path encompasses the origin
it has to cross the seam and thus gains an angle $\phi$.

Since this failure of parallel transport is a geometric property, we say that all the geometric information of the cone is centered in one point, because inclusion of that point in the path makes or breaks the angle.

### Less pointy cone

As we see, the thing we then need to change in order to get a more smooth cone holonomy is the tip. At the moment we have only one point which is
   problematic. This can be seen as our idealization: an infinitely sharp cone
   instead of a blunt one.

When we blunt the cone, we suddenly see that the path can be continuously deformed to include the "seam". However, what we have gained in smoothness
   we have lost in mathematical simplicity: we no longer can easily relate the
   cone to the Euclidean plane. In order to describe the blunt cone, we need to
   describe it's _connection_ and do some differential geometry.

...

Now we see that the cone is good.

[[FQHE or anyon chapter|FQHE/anyon chapter]]

# Unresolved Issues

## What is the importance of the 2D idealization for the FQHE

The quantum hall effect has also been studied in three dimensions, see \[@Torres2020,Tang2019,Pavlosiuk2017].

Apparently it is not as straightforward as I thought, people have constructed the 3D fractional quantum hall effect, but it's rather difficult.

The difference-maker for whether an electron gas is 2D seems to be it's Fermi-surface topology.[[3D Quantum Hall Effect]]

# Citations I still need to use

[@Shech2015b]

[@Wilczek1982]

[@Rao2001]

[@Knapp2016]



# Footnotes

[^13]: As an exercise, check whether this group satisfies the axioms of a [[Group]]

[^12]: Technically the fundamental group is only defined at a specific point $x_0$. However, if the space is _path-connected_, roughly meaning that it is possible to draw a path between any to points in the space, the fundamental groups at all points are isomorphic. All the spaces under consideration are path-connected, so I leave out this detail. An example of a non-path-connected space is the real line minus the origin, $\mathbb{R} - 0$. It is impossible to draw a path between any point $<0$ to one $>0$.

[^11]: It turns out that the 1-exchange do not turn out to be a separate path, or at least it does not change the number of possible paths, since $2*\aleph_0=\aleph_0$. There are a number of different ways to show this more exactly, but the easiest is to note that $RP^1$ is homeomorphic to the circle, and the 1-exchange is not a separate path there.

[^10]: This makes it somewhat difficult to visually relate the "one particle standing still" picture to what the configuration space actually represents. Roughly, you can imagine it as the "moving" particle returning back to its original position after a rotation of $\pi$ radians.

[^9]: Another way of thinking about this is to consider one particle to be fixed and the other moving around it.

[^8]: The other framework for considering such exchange is in terms of exchanging all the relevant quantum numbers, effectively mathematically swapping the particles. We shall see that this does not work for defining anyons.

[^7]: Note that this does not directly follow: it could also be the case that particles just sometimes have -1 and other times +1. Empirically, however, we find no such distinction, only dependent on particle type.

[^6]: The non-dirty sample just discussed is a great example of taking an idealization too seriously: we cannot explain the phenomena in the idealized setting, and have to retrofit extra physics on top of the idealization in order to get a satisfying explanation, only for us to then show in the limit of no impurities we regain our initial idealization. If this limit would not have been smooth (it fortunately is), we would have wasted all this time!

[^5]: Improved performance of impure 2D materials is an active area of research in material science, see \[[@Wang2020]] for a summary of how impurities enhance the conductivity of graphene.

[^4]: Or an infinite number of new particle types, depending on one's preference.

[^3]: The LWF might appear to just be an easy to compute with exemplar of this universality class, but it actually has some other nice features which set it apart from its siblings, see `other nice feature of LWF`

[^2]: Scare quotes, as the derivation clearly does not rely on experimental measurement alone. Unfortunately it is not possible to simply measure the number of electrons in a given area.

[^1]: If the reader was not aware of this yet, the author does hold such inclinations.
