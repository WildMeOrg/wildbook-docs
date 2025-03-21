# Code Contribition Guideline

Presently, Wildbook is a tomcat application leveraging jsp as the frontend. We are transitioning to a react frontend with a standardized REST API framework. We are iteratively removing jsp pages. For more details on the trajectory of page updates, see the [roadmap](roadmap.md).

## General
* DRY Principle: Do Not Repeat Yourself. Avoid code duplication by reusing components, functions, and styles. This not only minimizes the codebase but also simplifies maintenance and updates.
* If you are adding code that will be custom to a single platform, the feature needs to be approved by the Wild Me team. If approved, add all custom code in a block at the bottom of the page to prevent merge conflicts.
* Variable names should be in camel case
* Don’t use single-letter variable names (no matter how temporary you think the code is)
* Code should be clear enough to speak for itself without comments, but use your judgement on if a comment is necessary
* Code for clarity rather than for efficiency (one-liners are cool, but not at the expense of future obfuscation)
* URLs with multiple words should be in kebab case, i.e., `encounter-search`

### Dependencies
* All dependencies must be on a locked version. We do not accept PRs that use the `latest` version of anything.
* We use dependabot for dependency management; however, due to inconsistencies in semantic versioning and behavioral changes in packages supporting machine learning, we do system testing for all PRs suggested by dependabot. If you want to update or add a new dependency, contact the Wild Me team to discuss the changes before submitting a PR. 

### Internationalization
All Wild Me tools are intended for an international audience, so we want to provide translated versions. An active goal for 2024 is to get ensure that all product copy has been internationalized according to the following standard.

At present, in Wildbook, all copy except for site name and species names should be wrapped and localized to 5 languages: German, English, French, Spanish, and Italian. If you see UI copy that is not localized, let us know or create a PR to address the issue. 

### Notes during modernization
Because we are transitioning between tech stacks, there are some places where code is weird or where duplicate effort is necessary to maintain user experience.
* If updating the header, you will need to update:
  * `header.jsp`
  * `header.jsx`
  * `servletResponseTemplate.htm`

## React
### Plugins used
* `eslint-plugin-react`: For React best practices.
* `eslint-plugin-react-hooks`: Ensures correct use of hooks.

### Internationalization
Language files are located in `frontend/src/locale/`. If you are adding a new string to the system, make sure the string is available across the different languages by adding the key and translated string to 
* `de.json` - German
* `en.json` - English
* `es.json` - Spanish
* `fr.json` - French
* `it.json` - Italian
Ensure that the key is all caps with underscores as separators and is human-legible. Ex: **THISKEY_IS_GOOD** vs this.key.NeedsToBe-fixed vs TKNTBF

### Relevant rules
* Semicolons are required ("semi": 2).
* JSX is allowed in both .js and .jsx files ("react/jsx-filename-extension": 0).
* Console statements show warnings ("no-console": 1).
* React Hooks rules are enforced ("react-hooks/rules-of-hooks": "error").
* `/* eslint-disable no-restricted-globals */` must be present at the top of the serviceworker to allow `self` to work

### Best practices
* _Prefer Bootstrap Classes_: Always use Bootstrap's utility classes for styling when possible. This ensures consistency across the project and leverages Bootstrap's responsive features. Only use custom CSS or inline styles when the desired styling cannot be achieved with Bootstrap.
* _Code Consistency_: We are using eslint and prettier to enforce a consistent coding style throughout the project. This includes consistent naming conventions, file and folder structure, and code formatting.
* _Componentization_: Break down the UI into reusable components to maximize code reusability and clarity. Each component should have a well-defined purpose and should operate independently as much as possible.
* _State Management_: Carefully manage state to avoid unnecessary re-renders. Use local state (with `useState`) for data that affects only one component, and consider using context or state management libraries (like Redux or MobX) for shared state across many components.
* _UseEffect Best Practices_: When using `useEffect`, always include all dependencies in the dependency array to avoid bugs related to stale state and props. Also, be sure to return a cleanup function to avoid memory leaks, especially when subscribing to external data sources.
* _Props Validation_: Use `PropTypes` to validate props passed to a component, or consider using TypeScript for static type checking throughout the application. This can prevent many runtime errors and improve developer productivity.

### Tip and Tricks
* If bootstrap components are stubbornly refusing to change color, try `accent-color`.

### Customizing copy
If you are updating a translation for general use, do your PR against the `main` branch. If you are updating a language file to have specific copy associated with a specific platform, do your PR against the specific platform's branch.

## Java/jsp style

### Jsp Internationalization
`.properties` files in the `resources/bundles` language folders are used to generate translations for different supported languages. If you add a new string to the system, add the string to the appropriate `.properties` file, and make sure the string is available across `en`, `de`, `es`, `fr`, and `it`. Either provide the English string in all files, or provide the translated string in each one.

### Best practices
* If changing a dropdown in a .jsp page, use the library `select 2`. It provides a single line component update that adds in the ability to filter the dropdown. For example: `$('#selectCode').select2({width: '100%'});`
* Initialize variables and type signatures at the abstract/interface level when possible.

Instead of:

```{code-block} java
ArrayList encounters = new ArrayList<Encounter>();
...
public int getMax(ArrayList<int> numbers) {
```

Try:

```{code-block} java
List encounters = new ArrayList<Encounter>();
...
public int getMax(Collection<int> numbers) {
```

It’s easier to read and more intuitive for a function to take a Map or List than a HashMap or ArrayList.

The List interface defines how we want that variable to behave, and whether it’s an ArrayList or LinkedList is incidental. Keeping the variable and method signatures abstract means we can change the implementation later (eg swapping ArrayList->LinkedList) without changing the rest of our code.
https://stackoverflow.com/questions/2279030/type-list-vs-type-arraylist-in-java

Related: when writing utility methods, making the input type as abstract as possible makes the method versatile. See Util.asSortedList in Wildbook: since the input is an abstract Collection, it can accept a List, Set, PriorityQueue, or Vector as input, and return a sorted List.

* Runtime (not style): Use Sets (not Lists or arrays) if you’re only keeping track of collection membership / item uniqueness. 

Instead of:

```{code-block} java
List<MarkedIndividual> uniqueIndividuals = new ArrayList<MarkedIndividual>();
for(Encounter currentEncounter: encounters){
	MarkedIndividual currentInd = enc.getIndividual();
	if !(uniqueIndividuals.contains(currentInd)) {
		uniqueIndividuals.add(currentInd);
		doStuff();
	}
}
```
      			
Try:

```{code-block} java
Set<MarkedIndividual> uniqueIndividuals = new HashSet<MarkedIndividual>();	
for(Encounter currentEncounter: encounters){
	MarkedIndividual currentInd = enc.getIndividual();
	if !(uniqueIndividuals.contains(currentInd)) {
		uniqueIndividuals.add(currentInd);
		doStuff();
	}
}
```

The reason is a little deep in the data types. Sets are defined as unordered collections of unique elements; and Lists/arrays are ordered collections with no bearing on element-uniqueness. If the order of a collection doesn’t matter and you’re just checking membership, you’ll have faster runtime using a Set.

Sets implement contains, add, and remove methods much faster than lists [contains is O(log(n)) vs O(n) runtime]. A list has to iterate through the entire list every time it runs contains (it checks each item once at a time) while a set (especially a HashSet) keeps track of an item index for quick lookup.

* Use for-each loops aka “enhanced for loops” to make loops more concise and readable.

Instead of:

```{code-block} java
for (int i=0; i<encounters.length(); i++) {
	Encounter enc = encounters.get(i)
	doStuff();
}
```

try:

```{code-block} java
for (Encounter enc: encounters) {
	doStuff();
}
```

Note that in both cases you might want to check if `encounters == null` if relevant, but you rarely need to check if `encounters.length()>0` because the for-loops take care of that.

Conversely, if you want access to the `i` variable for logging or otherwise, the classic for-loop is best.


* `Util.stringExists` is shorthand for a common string check:

Instead of:

```{code-block} java
if (str!=Null && !str.equals("")) {
	doStuff();
}
```
 
Try:

```{code-block} java
if (Util.stringExists(str)) {
	doStuff();
}
```

This method also checks for the strings “none” and “unknown” which have given us trouble in displays in the past.

### Exception handling

* When dealing with any functionality that handles data persistence, make sure to use try catch exceptions. Data loss is considered a critical failure and an emergency to address.

* Try to catch exceptions as close to the problem as possible. For example, catching an exception of a single failing item _inside_ a loop is better than catching the exception outside the loop, causing the loop to exit early.

* Use a `finally` block, especially for clean-up functionality like closing database handles, etc.

* Recurring/predictable exceptions are often better handled by preventing them. For example, OpenSearch indexing will often throw exceptions for invalid data (for example, lat/lon out of range). However, _even though these are caught_, the caught exception still prevents the whole object from being indexed. Better to prevent the _single field_ from being indexed through code (validation) than let the exception happen.

