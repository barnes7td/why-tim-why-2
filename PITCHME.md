## Why Tim, Why?

### ...the big picture

---

### My Caveats

@ul

- The answers given here are...
  - Highly opinionated
  - They ARE NOT comprehensive

@ulend

Note:

- Billie may agree
- You may disagree
- Feel free to add to

---

### The Big Questions

Note:

- Good Dev = question the base assumptions
- This will help us convey our priorities

---

### Why Angular?

@ul

- Conversion started with Angular.js
- We needed an upgrade
  - ES6 syntax/TypeScript/Bootstrap
  - Testing
  - Performance

@ulend

Note:

- We really wanted to use the modern syntax.
- Bootstrap: flexbox baked in
- Testing wasn't built in to Angular.js. It was an addon
- Performance: Watchers, Lazy Loading

---

### Why Angular?

**Watch Out**

@ul

- Larger framework library
  - React.js and Vue.js are smaller
- Angular is opinionated
  - Angular dictates
  - Everything's a Service.

@ulend

Note:

- Angular dictates subsequent whys
- Dictates: Routing
- Dictates: Services

---

### Why 2 Apps?

@ul

- **Faced with**
  - Flash in the browser ending 2020
  - Several features still to convert
- We needed and wanted Angular's features
- We looked at upgrading
  - Angular.js inside of Angular

@ulend

Note:

- We didn't have time to upgrade the whole app
- We had to get the rest converted
- Remember we wanted the newer features
- Upgrading: Had a POC, Still too much would have had to be rewritten on the Angular.js side
- Not in components, Were using factories

---

### Why 2 Apps?

**Why We Decided**

@ul

- Herff has a suite of applications
- Routing between apps - Deep Linking
- Already systems for Deep Linking
- Decided to keep complexity in the routing
- Gave us a quick way to transition
- We thought the Angular.js was going to be deployed

@ulend

Note:

- Portal, etc.
- Deep Linking - routing to specific internal pages, sometimes with state
- Home, Master List, Book Setup, Library, Catalog

---

### Why 2 Apps?

**Watch Out**

@ul

- We must keep 2 separate headers in sync
  - with different style sheets
- The 2 apps use VERY different patterns
  - Advice given doesn't transfer
- In the Angular.js
  - Live updating is not easy
  - Data integrity was a problem

@ulend

Note:

- What you do to one header has to be duplicated in the other, but different
- similar/same class names, different visual results
- Different Advice
  - I advocated using functions on watchers in A.js
  - We did more one-way binding
- Data Integrity
  - 1 giant data object, nested, with duplicate values

---

### Why Redux (ngrx)?

@ul

- Good arguments against
  - ngrx is takes too much boilerplate code.
  - Related code is spread throughout multiple files.
  - Everyone has to change how they think about code.

@ulend

Note:

- Boilerplate: Action, Reducer, Selector, State
- Imperative to Reactive
- statefull to functional
- To simplify all there is not a concepts of facades

---

### Why Redux (ngrx)?

**Why We Decided**

@ul

- Redux is good...
  - When here is lots of shared state across modules
  - For handling the live updating (SSE)
- In the Angular.js code
  - The biggest issue we faced involed shared state
  - Data integrity
  - Data duplication
  - Multiple services were modifying global state (in different ways)

@ulend

Note:

- across modules = across routed components
- SSE: just update the store
- Optomist update: update the store, before the API returns success
- Different advice
  - Global state bad/Redux makes it safe

---

### Why Redux (ngrx)?

**Watch Out**

@ul

- Mutation is bad
- You have to make a choice when to switch from reactive to imperative
  - subscribe vs async
  - container component binding a child presenter
- Boilerplate obscures the intention of the code.

@ulend

Note:

- Mutation in the store area
- Must create a new object, for protection (one-way)
- Redux doesn't actually keep you from mutating
- Choices: Why we've move away from binding and presenter components
- Communication of Intention to other Coders -> Single most important factor in good code.

---

### Why we chose Fabric.js?

@ul

- The flex app directly modifies an svg
- Fabric.js uses the HTML Canvas API

@ulend

Note:

- Couldn't we just modify the svg.js

---

### Why we chose Fabric.js?

**Why We Decided**

@ul

- Deadline was short
- fabric.js gives us so much out of the box.
- fabric.js is a stable library
- fabric.js was written for the Page Design scenario
- Was considered:
  - fabric.js / svg.js hybrid

@ulend

Note:

- Deadline: Summer of 2019
- Fabric: selection, handles, filters
- Zoom and Pan syncing across libraries is untested.
- Bouncing object back and forth may have created position errors.

---

### Why we chose Fabric.js?

**Watch Out**

@ul

- Fabric.js relies on mutation
- Performance problems? with multiple canvases

@ulend

Note:

- Mutation doesn't work with Redux

---

### Next Time: Part Deux

- More Whys!
- Why we save things in the store as a dictionary (not arrays)
- Why we have Core/Shared
- Why we use modules
- Why we think Presenter components are rarely useful
- Why we DO repeat ourselves inside of test files.
- Why we prefer shallow nesting as a general strategy
- Why we have components talk to effects and not services directly

---

### Questions?
