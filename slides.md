class: middle

# Built to Last

#### A domain-driven approach to beautiful systems

---

class: middle background-color-delorean

## Welcome to your first day at Delorean! 🚗💥🕖

It's like Uber... for time travel!

???

Welcome to your very first day at Delorean! Together, we are
revolutionizing the very industry of time travel! With one touch on our
app, you can now summon a driver to whisk you away to any time period
you wish.

We're changing the world, indeed.

---

class: background-color-delorean

## And it's a hot mess!

We moved a teensy bit too fast:

1. Too many teams in one codebase

???
Oh by the way, I should mention you might be a little surprised when
you open our monolithic codebase. It's just got a few little quirks
I'm sure you won't mind, heh heh. I mean, we have a lot of teams working
on this codebase, so there's gonna be a lot of commits flying through at
once.

--
2. Changing a feature changes multiple codebases

???
We have several of these big ol codebases, so our features are going to
have to be coded across several systems to coordinate a big release! No
big deal, you'll get used to it.

--
3. Concepts inconsistently named

???
Finally, there are some funny naming conventions here and there, so when
your PO tells you about the FizzBangWidget, just don't forget it's
actually the FooBarDoohickey which someone named the BarThingamabobber a
few years ago. Don't worry, he's not with the company anymore, haha!
That's another story for another time.

--
4. Ship, ship, ship! (No time to refactor)

???
I know what you're thinking, you're thinking we need to fix things up a
little bit around here. Well I can assure you we have plans to do
something about it right around the corner, but for now we've really got
to ship our newest feature, Puppy Deliveries. Your team will fill you in
on it in a bit. Well, it's time for standup, it's great having you on
the team!


---

class: middle center

## Hi, I'm Andrew

Friendly neighborhood programmer at Carbon Five

---

class: middle center background-color-code

<img src="http://www.carbonfive.com/images/c5-logo-vertical.png" alt="Carbon Five" height="20%" />

---

## I've been thinking about beautiful systems

In the language - elegance, syntax, form, expressiveness

--

In the tooling - developer ergonomics

--

In the tests - test practices & coverage

--

In its **longevity** - built to adapt to and embrace change

???

I've oftentimes thought that beautiful systems were composed of the form
of the code - in its style, or in how developers would sit down and
interact with it, or in how well it sat in tests.

However, I've had the thought lately that a good measure of a beautiful
system is its longevity.

---

## Lasting systems - what they are

Flexible and easy to change, to adapt to changing biz requirements.

--

Easily maintained - loosely coupled, and highly cohesive

--

Resistant to the Dreaded Rewrite

???

It's not throwaway, but like all systems, it's not overengineered with
the expectation that it must last forever

---

## Lasting systems - what they are not

So terrible, nobody wants to work in it.

--

So terrible, they cripple the business.

???

Lasting systems are NOT systems that are so crappy that you can't change
them, and so everybody avoids it and it lives forever like a nightmare.

Lasting systems are NOT systems that are so tangled that the business
literally cannot function without it. Unrescuable?

---

class: middle

### Information hiding

*D.L. Parnas - "On the Criteria to Be Used in Decomposing Systems into Modules"*

???

So I went looking for some inspiration, and learned about Parnas' work
about modularization in the 1970s, words that stand still today.

In this paper, he took a look at a program that did text processing and
compared two approaches - one that divided up its processing
responsibilities by its procedural components, do A, B, then C, and
another one that was responsible for the individual design decisions to
do various things like scan for words, storing data in internal data
structures, etc.


---

class: middle center background-image-contain background-white

background-image: url(images/parnas-paper.png)

---

class: middle

"We propose instead that one begins with a **list of difficult design decisions** or **design decisions which are likely to change**." (Emphasis added)

???

His point was that modules need to hide away minute implementation
details from other modules - things that are likely to change!

--

"Each module is then designed to hide such a decision from the others."

---

## From software program to the entire system

Where are the difficult design decisions in this company that are likely to change?

???

Even though Parnas' paper looked at a single program and attempted to
rethink its division of labor from flow to responsibility, we can take
this one step further and ask ourselves - how can our systems hide the
complexity of the decisions of each business organization from each
other?


--

#### Within the business groups that generate them!

---

## A peek into the life of our systems:

* Marketing wants us to generate 5000 promo codes

--
* Finance needs us to implement a new audit log

--
* Product teams want us to launch new food delivery features.

--
* Marketing wants us to invalidate 2000 of the 5000 codes

--
* Finance needs us to add another attribute to the audit log

--
* Product teams want us to launch food delivery in a second market
--

#### (That sounds like change!)

---

## The landscape of Rails code:

PLACEHOLDER: diagram of app folders

Show app growing over time as app code drops in.

---

## How do we get out of the world of the monolith?

So... just do microservices?

What do I extract?

What if I extract something that's too specific? Too generic?

???

I used to work at a Rails shop that had a massive monolith.

I wished for an insight that would help me understand what exactly
belonged where, or gave me general insights toward.

---

class: middle

### A rule of thumb: design systems around your organizational structure!

Remember Conway's Law?

???

I want to put forth that a good rule of thumb is an organizational
pattern that isolates business processes from others.

---

class: middle

## Introducing Domain-Driven Design

DDD is both a set of high-level design activities and specific software patterns

PLACEHOLDER: book image

???

First came out as a book in 2003: Domain Driven Design by Eric Evans.

It can be very confusing as it's got a lot of concepts and
enterprise-speak.

---

class: 

## Our goals today

📖 **Develop a shared vocabulary** with our business partners

--

👓 **Visualize our system** from a domain perspective

--

✏️ **Discover the hidden boundaries** in our system(s)

--

🛠 Do a little bit of **refactoring**

???

We'll learn to see the software from the business domain perspective

Visualization is important: you can't improve what you can't see!

This is a team exercise! If you're doing any of these alone by yourself
because you're the Lead, or the Architect, you're doing this wrong. This
is meant to be a communal, team-wide effort.

---

class: middle center

## Strategic Design

#### Through an exercise called Context Mapping

???

Everybody say "Strategic Design"

We are going to go through an exercise called Context Mapping.

---

### Problem statement

Systems too often become unmaintainable because there
are imprecise, lazy names between code and the business.

---

#### Apply It! 🤖

## Develop a Glossary

Get your business domain experts and technical staff together in a room
and build a definition list of the concepts and the actions in your
domain.

???

Domain-Driven Design hinges on precise language and terminology.

I know this probably isn't what you showed up for, but I want to drive
home the point that long-lasting, beautiful systems have precise terms
that dutifully map to real concepts in the business.

---

## Glossary

Nouns - concepts (a.k.a. entities)

Verbs - actions (a.k.a. events)

---

#### A sample glossary

Driver: [Entity] A customer equipped with a car, focusing on providing driver services

--
<strike>Passenger</strike> Participant: [Entity] A person seeking a ride to a
specified location.

--

 HailedDriver: [Event] A user has signaled their intent to seek out a ride.

--

 ChargedCreditCard: [Event] A customer credit card has been charged for a transaction.

???

Here's the interesting part - you may find yourself talking through the
intricacies of each model. Some of these may be assumed, emergent terms
you've developed over the years at your company. Good - the point is to
get it actually documented.

Another benefit we get here is the ability for new engineers and product
people to onboard quickly and get used to what your team does.

Now put this up on a wall, or on a wiki! Somewhere where the team can
continually reference in the future.

---

### That's a Ubiquitous Language

Rename concepts in code

Only applies to a context of the business


???

Now you can go and rename misnomers in the code.

---

### Problem statement:

We often don't know how to refactor our systems
because we lack a high-level view of it.

---

#### Apply It! 🤖

## Visualize Your System

Let's generate an ERD diagram!

I like to generate mine with a gem like [`railroady`](https://github.com/preston/railroady) or
[`rails-erd`](https://github.com/voormedia/rails-erd)

If you have multiple systems, do this for each system.

???

We often don't know how to refactor our systems
because we lack a high-level view of it. Luckily, we have some tools at
our disposal. I'm partial to using Railroady, or Rails ERD to get a high
level view of our system.

Caveat: this is a bottom-up design view of the system, and there is also a
place for top-down design.

Secondly - this may not necessarily be the "right" level of indirection
of your system - as it's solely generated off of AR relationships. You
may need to actually build this by hand by taking an inventory of your
system, the business objects and how they're used.

I prefer to use this approach when I first enter a system because, quite
frankly, it's virtually free, and it gives us enough raw material to
proceed.

---

class: middle center background-image-contain background-white

background-image: url(images/erd.png)

---

class: middle center

### Yikes.

---

#### Definition! 📖

### Core domain

The **Core Domain** is the thing that your business does that makes it unique.

--

Delorean Core Domain: **Transportation**

???

Now we're going to get into the nitty gritty of DDD - really elucidating
what defines our domain boundaries. Every software system generally
serves to fulfill its purpose in a certain operational category.

Here at Delorean, we focus on transportation.

---

#### Definition! 📖

### Supporting domains

A **Supporting Domain** (or Subdomain) are the areas of the business
that play roles in making the **Core Domain** happen.

--
* **Driver Routing** (route me from X to Y)

--
* **Financial Transactions** (charge the card, pay the driver)

--
* **Optimization & Analytics** (track business metrics)

--
* **Customer Support** (keep people happy)

???

Now a subdomain is anything that supports the core domain. These are
ancillary functions, but important to help the business do its core
thing properly.

See anything interesting here? Most likely, these domains have a company
unit devoted to them.

In many companies, each of these organizational units have their own
dedicated engineering staff.

---

class: middle

#### Apply It! 🤖

## Discover the domains on your diagram

Look for clustered groupings.

You might discover some domains you never even thought you had!

???

So here's where we roll up our sleeves and get messy. Let's print out
our ERD diagram and paste it on the wall, and get messy.

Take out a pen, or whiteboard marker and draw areas of your
system that correspond to certain domains. In the Subdomain section
before, you can

---

class: middle center background-image-contain background-white

background-image: url(images/erd.png)

---

class: middle center background-image-contain background-white

background-image: url(images/erd-2-domains.jpg)

---

## Top-down or bottom-up?

We did a bottom-up discovery here.

???

Go ahead and draw your subdomains over each of the models.

Top down:

* a simple scheme for your business, or
* you've got a pretty good idea of how to do this.

If you already know what your business subdomains do, you can
attempt to overlay your subdomains over the diagram, or even make sticky
note diagrams over them.

Bottom-up context mapping:

Looking at our ERD diagram, we allow groupings and patterns guide us to
the invisible markers and lines between domains in our systems.

You may even see some domains you haven't thought of before!

In a bottom-up manner of context mapping, we are going to allow the
diagram to guide us to these invisible groupings. We should see some
clusters of models - these are places to stop and dig into and ask
ourselves, "what business function does this relate to"?

---

class: middle center background-image-contain background-white

background-image: url(images/erd.png)

---

class: middle center background-image-contain background-white

background-image: url(images/erd-2-domains.jpg)

---

class: middle

### Congrats - we've got a list of domains in our system

And a rough mapping of what domain models go where.

---

class: middle

## Now let's talk boundaries

Boundaries in Rails:

1. The Rails App

--
2. Gems

--
3. Modules

--
4. Classes

--
5. External API

--
6. Rails Engines

--
7. A separate app

---

#### Definition! 📖

### Bounded Contexts

A **Bounded Context** is:

- Concretely: a software system (like a codebase)
- Linguistically: a delineation in your domain where concepts are "bounded", or contained

???

Remember, this is because we agreed that different domains may have
different concepts, and hence different Ubiqutious Languages.

---

## Bounded Contexts give us linguistic clarity

Big idea: each domain (business function) has a different view of the
world, often conflicting.

Bounded contexts allow these concepts to coexist.

???


---

## Overloaded concept: Trip Time

Financial Transaction Context: Trip time is calculated from **vehicle moving time (minutes)**

Routing Context: Trip time is calculated from **total passenger
minutes**

--

Note that these concepts share the same name, but have nuanced
behaviors based on context!

---

## Overloaded concept: Trip Cost

Financial Transaction Context: How much $ the customer pays
(dollars)

Routing Context: Trip efficiency (miles moving time / time in car)

--

Note that these concepts share the same name, but are wildly
different!

---

class: background-color-code

```ruby
# Overloaded concepts!
class Trip
  def cost
    # Routing: Routing AI subsystem efficiency metric
    # Financial: $$$ metric
  end

  def elapsed_time
    # Routing: total clock minutes
    # Financial: moving minutes
  end
end
```

???

Bounded Contexts give us code clarity

Multiple domains overloading the same model

The big idea here is that there is no one True View of the world here.
By breaking the system up into different Bounded Context systems, free
up the cognitive landscape of business terms to roam free without
running into other terms.

True DDD practitioners will encourage us to listen to the domain and use
linguistic drivers to develop these systems even further.

Anyways, that's more reason to split up our system into multiple
systems, but we won't elucidate upon it too much here.

---

## Bounded Contexts are software systems

We mean that they are real software systems that encode real concepts in code.

---

## Bounded Contexts are linguistic boundaries

Bounded Contexts limit the *applicability* of each model, term, or idea.

You won't have all the Bounded Contexts you need at the moment, but
that's an ideal world we'll drive toward.


---

#### Apply It! 🤖

## Overlay your bounded contexts

Next up - with a different color pen or marker, draw lines around system
boundaries / bounded contexts.

--

You may also find other system boundaries like:

* External cloud providers
* Other teams' services or systems

---

class: middle center background-image-contain background-white

background-image: url(images/erd-2-domains.jpg)

---

class: middle center background-image-contain background-white

background-image: url(images/erd-3-bounded-context-simplified.png)

---

class: middle center background-image-contain background-white

background-image: url(images/erd-4-bounded-context-extended.png)

---

## Draw out the dependencies

Draw lines indicating data flow directionality

**U**pstream/**D**ownstream

???

Using simple arrows, draw lines indicating data flow directionality
between systems (upstream and downstream relationships).

---

PLACEHOLDER: context map directionalities

---

## You just made a Context Map!

A **Context Map** gives us a place to see the current system as-is (the
problem space), the strategic domains, and their dependencies.

---

## Making sense of the Context Map

We may notice a few things:

--

* One bounded context contains multiple sub-(supporting) domains

---

class: middle center background-image-contain background-white

background-image: url(images/erd-4-bounded-context-extended.png)

---

## Making sense of the Context Map

We may notice a few things:

* One bounded context contains multiple sub-(supporting) domains
* Multiple bounded contexts are required to support a single domain

???

Note upstream vs downstream dependencies. These are communication bottlenecks.

---

class: middle center background-image-contain background-white

background-image: url(images/erd-4-bounded-context-extended.png)

---

class: middle

## An Ideal Architecture

Each **Domain** should have its own **Bounded Context**

Key concept in DDD!

???

A one-to-one mapping is important because it maximizes flexibility for
domain concepts to breathe within their own enclosed systems.

---

class: middle center background-image-contain background-white

background-image: url(images/erd-5-bounded-context-ideal.png)

---

class: middle

## Increased cohesion!

We just found the areas where code "naturally" fits together, because
they are serving the same business goal.


???

We just found the areas where code "naturally" fits together, because
they are serving the same business goal.

We will find that these entities naturally prefer each other, since
they live in the same organizational unit.

---

#### Apply It! 🤖

## Break your application into domain modules

Incremental refactoring, using Ruby Modules to lead the way!

---

class: middle background-color-code

```ruby
class Trip < ActiveRecord::Base
  belongs_to :vehicle
  belongs_to :passenger
  belongs_to :driver
end

class TripsController < ApplicationController
  # ...
end
```

???

Here we start with a typical Rails controller. We've picked the `Trip`
concept and decided to move it to `Ridesharing`.

---

class: middle background-color-code

```ruby
module Ridesharing
  class Trip < ActiveRecord::Base
    belongs_to :vehicle
    belongs_to :passenger
    belongs_to :driver
  end
end

module Ridesharing
  class TripsController < ApplicationController
    # ...
  end
end
```

???

A simple refactoring step is to pick it up wholesale and move it into
its own module directory.

---

class: middle

#### Find references to newly modulized classes and change them.

---

class: middle background-color-code

```ruby
# config/routes.rb

resources :trips
```

---

class: middle background-color-code

```ruby
# config/routes.rb

namespace :ridesharing, path: '/' do
  resources :trips
end
```

---

class: middle background-color-code

```ruby
class Invoice
  belongs_to :trip
end
```

---

class: middle background-color-code

```ruby
class Invoice
  belongs_to :trip, class_name: Ridesharing::Trip
end
```

---

## Creating domain-oriented folders

```
app/domains/ridesharing/trip.rb
app/domains/ridesharing/service_tier.rb
app/domains/ridesharing/vehicle.rb
app/domains/ridesharing/trips_controller.rb
app/domains/ridesharing/trips/show.html.erb
```

---

class: middle center background-image-contain

![Cohesion illustration](images/cohesion_illustration.png)

---

## More advanced concept - when you have one model that needs to go two places

Sometimes, you have a concept that needs to be broken up:

---

class: background-color-code

```ruby
module Ridesharing
  class Trip < ActiveRecord::Base
    def cost; end
    def length; end
  end
end

module FinancialTransaction
  class Trip < ActiveRecord::Base
    def cost; end
    def length; end
  end
end
```

???

What do you do with a model that needs to go two ways?

TODO

---

## ActiveRecord relationships can be abused!

Objects start knowing too much about the entire world.

"God Objects"

---

class: middle background-color-code

```ruby
class PaymentConfirmation
  belongs_to :trip, class_name: Ridesharing::Trip
  belongs_to :passenger, class_name: Ridesharing::Passenger
  belongs_to :credit_card
  has_many :menu_items
  belongs_to :coupon_code
  has_one :email_job
  # ad infinitum...
end
```

---

class: middle center background-image-contain background-white

background-image: url(images/aggregate-root-1.png)

---

class: middle

## Aggregate Roots

**Aggregate Roots** are top-level domain models that reveal an object
graph of related entities beneath them.

--

Can be considered a **Facade**

---

class: middle center background-image-contain background-white

background-image: url(images/aggregate-root-2.png)

---

## Decrease coupling by only exposing aggregate roots

Make it a rule in your system that you may only access another domain's **Aggregate Root(s)** via:

* Direct method calls
* JSON payloads
* API endpoints

--

Internally, it's OK to reach for whatever you need.

???

Identify models that are aggregate roots - these should be clustered in
the ERD diagram you generated.

Each context may have several Aggregate Roots - that's OK. Just limit
outside callers from using them.

Beware of taking the easy way out and shipping subresources around, both
in direct method calls, API payloads, event bus payloads.

---

class: middle

## Build service objects that provide Aggregate Roots

Break dependencies on AR relationships

Your source domain can provide a service (Adapter) that returns the
**Aggregate Root**

???

Ship these around when communicating between domains!

---

class: middle background-color-code

```ruby
# Provide outside access to a core model
# for the Ridesharing domain
module Ridesharing
  class FetchTrip
    def call(id)
      Trip
        .includes(:passenger,
                  :trip, ...)
        .find(id)
      # Alternatively, return something non-AR
      # OpenStruct.new(trip: Trip.find(id), ...)
    end
  end
end
```

---

class: middle background-color-code

```ruby
# In the old world, we relied on AR relationships:
module FinancialTransaction
  class PaymentConfirmation
    belongs_to :trip, class_name: Ridesharing::Trip
    belongs_to :passenger, class_name: Ridesharing::Passenger
    # ...
  end
end
```

---

class: middle background-color-code

```ruby
# Now, cross-domain fetches must use the
# aggregate root service:
module FinancialTransaction
  class PaymentConfirmation
    def trip
      # Returns the Trip aggregate root
      Ridesharing::FetchTrip.new.find(payment_id)
    end
  end
end

# OLD: payment_confirmation.passenger
# NEW: payment_confirmation.trip.passenger
```

???

Now in this new world, cross-domain access to a Trip is only doable from a service object that you call.

---

class: middle

## Decrease coupling by publishing events for async dependencies

Domains that only need unidirectional data flow work well here!

???

Let's think of another way to decouple our systems - via an event-driven
architecture.

Many of your companies are already doing this - you may have existing
subsystems like RabbitMQ or ZeroMQ - that allow asynchronous message
bus-like communication between systems.

For the rest of us - I'm about to introduce something that piggybacks
off of an asynchronous processing system that we already have - Sidekiq.

---

class: middle

## Just send an event notifying the outside world!

Instead of needing to know about the outside world, we simply
publish an event.

---

class: middle background-color-code

```ruby
# Old way
class TripController
  def create
    # ...
    ReallySpecificGoogleAnalyticsThing
      .tag_manager_logging('trip_created',
                           ENV['GA_ID'],
                           trip)
  end
end
```

---

class: middle background-color-code

```ruby
class TripController
  def create
    # ...
    DomainEventPublisher.new
      .call(:trip_created, trip.id)
  end
end
```

---

## Introducing Rails events via the wisper gem

```ruby
class DomainEventPublisher
  include Wisper::Broadcaster

  def call(event_name, *event_params)
    publish(event_name, *event_params)
  end
end
```

---

## Every bounded context has its own event management system

Now we add an event handler for each domain, so it knows how
to handle incoming events.

Anti-corruption layer. Each incoming event that this domain must respond
to will be subscribed to here, and dispatched accordingly.

---

class: background-color-code

```ruby
module Analytics
  class CommandDispatcher
    include Wisper::Subscriber

    # Method name is invoked based on the name of the message.
    # So this method is invoked in response to the `trip_created` event.
    def trip_created(params)
      # handle the action here, delegate out to a service object.
      LogTripCreated.new.call(params)
    end
  end
end
```
---

class: background-color-code

```ruby
# And now, we can encapsulate the logging concerns
# for trip creation in a service
module Analytics
  class LogTripCreated
    def call
      ReallySpecificGoogleAnalyticsThing
        .tag_manager_logging('trip_created',
                             ENV['GA_ID'],
                             trip)
    end
  end
end
```

---

class: background-color-code

```ruby
# Different domains can opt to subscribe to the same
# events!
module FinancialTransaction
  class CommandDispatcher
    include Wisper::Subscriber

    def trip_created(params)
      CreateTaxAuditLogEntry.new.call(params)
      DeductGiftCardAmount.new.call(params)
    end
  end
end
```

---

### Think event-driven if

* You don't have to manage rollbacks, transactional consistency
* Your downstream systems can accept eventually consistent data

---

### Now make it truly asynchronous with -- Sidekiq!

Wisper can hook into Sidekiq to truly process your events
asynchronously in a worker queue.

---

### Or, you can build this yourself with a true MQ system

Shoutout: Stitch Fix's [Pwwka]() is an excellent job queueing system.

---

### A true event-driven model can be taken even further

See: Event Sourcing, Event Storming, Event Store

???

We won't go into these models, but they can help systems scale cleanly.
But they also require a very large overhaul of your existing data model
and can be hard to implement.

---

## Conway's Law and DDD

Conway's Law, paraphrased: "Software systems tend to look like the
organizations that produce them"

--

DDD modeling oftentimes reveals domains that follow organizational
layouts.

Your software systems follow organizational optimizations.

--

Thus this is a very natural place to draw a seam!

???

The organization has optimized for communication within itself,
and has likely reduced its dependencies on other organizational units.

---

## Cohesion as a factor of business change

The Context Map helps you understand where change is most likely to
cluster - from the business functions that drive them.

Thus, we organize our code anticipating such change together.

---

## Systems thinking

Systems thinking is a process tool that forces us to think about our
systems as living, breathing organisms.

Systems built to last will take those factors into account - identifying
work producers, minimizing waste, increasing efficiencies, localising and clustering work.

---

## The evolution of this localised change...

1. Domain-oriented folders, to...
2. Rails engines, to...
3. Rails microservices with a shared AR gem and a message queue, to...
4. Fully-decoupled, polyglot microservices

Each of these evolutions is simply modeling a bounded context with
stronger seams!

"Component-Based Rails Applications" by Stephan Hagemann

---

## Warning: Limitations apply!

Don't try to do this on every project!

--

I've been guilty of overdesigning.

--

Try it out, step by step

--

Back it out if this doesn't "fit"

???

Here's what you can do: spike it out.
See how it feels and fits. Back it out if it doesn't work for you.

---

class: middle

## What we did tonight

👓 **Visualized our system** with a Context Map

✏️   **Drew boundaries** in our code!

🛠 Do a little bit of **refactoring** with domain modules, Aggregate
Roots and Domain Events.

---

class: middle

Sample code: [https://www.github.com/andrewhao/delorean](https://www.github.com/andrewhao/delorean)

---

class: middle

## Thanks!

Github: [andrewhao](https://www.github.com/andrewhao)

Twitter: [@andrewhao](https://www.twitter.com/andrewhao)

Email: [andrew@carbonfive.com](mailto:andrew@carbonfive.com)

---

## Prior Art

* W. P. Stevens ; G. J. Myers ; L. L. Constantine. ["Structured Design"](http://ieeexplore.ieee.org/document/5388187/) - IBM Systems Journal, Vol 13 Issue 2, 1974
* Evans, Eric. [Domain Driven Design](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215)
* Vernon, Vaughan. [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)
* http://www.win.tue.nl/~wstomv/quotes/structured-design.html#6
* https://www.infoq.com/articles/ddd-contextmapping
* http://gorodinski.com/blog/2013/04/29/sub-domains-and-bounded-contexts-in-domain-driven-design-ddd/
