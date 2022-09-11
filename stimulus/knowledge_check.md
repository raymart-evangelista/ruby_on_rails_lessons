# Knowledge Check
- When do you use Stimulus?
  - The majority of cases is when you want to manipulate elements--automatically connecting DOM elements to JS objects
  - when you want to manipulate an existing HTML doc which can mean adding a CSS class that hides an element or animates it or highlights it, OR it can mean rearranging elements in groupings, OR it can mean manipulating content of an element like when transforming UTC times that can be cached into local times that can be displayed, OR it can even mean creating new DOM elements

- How do you select a DOM element?
  - first, add `data-something-target` to an HTML element
  - in the controller, declare it with `static targets = [ "something" ]`
  - use `something` in the controller with `this.SomethingTarget` or `this.SomethingTargets`
  - use `data-action` attributes execute JS to react instead of `querySelector`

- How do you make your Stimulus controllers reusable?
  - you can configure the controller with an attribute to specify the CSS class to be used

- How do you trigger actions on an event?
  - use `data-action="action->controller#method"`