# MVP vs MVC

This mini-sprint will get you familiar with the design patterns MVP and MVC, as well as the differences between them.

Keep in mind that MVC is a very overloaded term; you might see wildly differing opinions if you research it across the internet. The point of this sprint is not to memorize the "one true way" of doing MVC/MVP. Instead, the goal is to start thinking about the **semantics** of code, and begin understanding the **interactions** between *different kinds* of code within your own projects.

With that in mind, here are some resources you can read on your own time for MVC vs MVP:

- [Exploring MVC, MVP, and others](http://www.infoworld.com/article/2926003/microsoft-net/exploring-the-mvc-mvp-and-mvvm-design-patterns.html)
- [MVC vs MVP](http://www.codeproject.com/Articles/288928/Differences-between-MVC-and-MVP-for-Beginners) (read up until "Defining Communication Interface")

## Getting Started

Open up `index.html` in your browser and take some time to explore the code. Afterwards, answer the following questions with your partner.

## Model Questions

Take a look at `src/models.js` and answer the following questions:

1. How many Model methods emit a change event? 3
2. How many emit no change event? Why wouldn't they? 1, because it doesn't change the peeps array
3. Why do you think this Model wants to keep the `peeps` data encapsulated? so that nothing else can modify it

## MVPresenter Questions

Take a look at `src/m-v-presenter.js` and answer the following questions:

1. How many View events does Presenter listen for? 2
2. How many Model events does Presenter listen for? 1
3. Where does everything start? In other words, where does the View actually get put on the page? the mount function
4. What are the responsibilities of the Presenter? listen for click events and tells model to change itself
5. What are the responsibilities of the View? to append html on the page

## MVController Questions

Take a look at `src/m-v-controller.js` and answer the following questions:

1. How many controller actions are defined? 1
2. How many controller actions does the View bind to itself? Where? 1, on line 26
3. How many Model manipulations does the View do on View events? Where? 1, on line 40
4. Where does everything start? In other words, where does the View actually get put on the page? the render function, line 51
5. What are the responsibilities of the Controller? rotate the roster
6. What are the responsibilities of the View? removes people from roster

## Software Design Questions

1. Why is it "bad practice" for a model to directly update the view? makes code less orgnaized, difficult to read and debug
2. What are some benefits for forcing the model to know nothing about the view? it can't accidently change the view and the view can't accidently change the model's data

## Exercise

For both MVP and MVC, implement a form that allows the user to create a new person.
