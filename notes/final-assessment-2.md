# FEW 2.3 Final Assessment

Your goal is to create a React application with the components and features described below.

The Problems below are presented in order of complexity. Doing them in order will be easier. 

Complete each step to the best of your ability. I have listed a point value for each step. Solve as much of each step as you can partial credit will be awarded. 

Do not post this project to GitHub! Instead you will submit your work to me by first **removing the node_modules** folder then copying your work to my USB drive.

## Getting started (10pts)

Your final assessment is a React Project.

Create a React Project and name it with 'final' and your first and last name:

`final-<first>-<last>`

I should be able to run your project with `npm start`.

## Home Components (10pts)

Create a **Home** component that displays your name and the name of this class.

Make a **Title** component, use it to display your name. The Title Component _should take a prop that sets the text displayed_ in the title.

In this step you are creating two Components `Home` and `Title` and using the `Title` component inside the `Home` Component to display your name. 

## Components moderate (10pts)

Create a 'Clicker' component. 

Create a new **Clicker** Component that displays a _button_ and an instance of the _Title_ component you created in the previous step.  

This component should count the number of times the button was clicked and display the count in the Title. Use state to track the count. 

When you're done with this step the Title should display an initial count of 0, and increase the count by 1 each time I click the button. 

## Components Patterns (20pts)

Display data from the Star Wars API. 

The Star Wars API is a simple API that takes a number and returns a JSON object describing a character in one of the Star Wars movies. 

For example:

`https://swapi.co/api/people/1/`

Returns: 

```JSON
{
    "name": "Luke Skywalker", 
    "height": "172", 
    "mass": "77", 
    "hair_color": "blond", 
    "skin_color": "fair", 
    "eye_color": "blue", 
    "birth_year": "19BBY", 
    "gender": "male", 
    "homeworld": "https://swapi.co/api/planets/1/", 
    "films": [
        "https://swapi.co/api/films/2/", 
        "https://swapi.co/api/films/6/", 
        "https://swapi.co/api/films/3/", 
        "https://swapi.co/api/films/1/", 
        "https://swapi.co/api/films/7/"
    ], 
    "species": [
        "https://swapi.co/api/species/1/"
    ], 
    "vehicles": [
        "https://swapi.co/api/vehicles/14/", 
        "https://swapi.co/api/vehicles/30/"
    ], 
    "starships": [
        "https://swapi.co/api/starships/12/", 
        "https://swapi.co/api/starships/22/"
    ], 
    "created": "2014-12-09T13:50:51.644000Z", 
    "edited": "2014-12-20T21:17:56.891000Z", 
    "url": "https://swapi.co/api/people/1/"
}
```

Create a new **StarWars** component that has a _text input_, a _button_, and a _Title_. Entering a number in the input and clicking the button should show the name of a Star Wars Character in the Title. 

Use fetch to make a request using the SWAPI api below, handle the response by displaying the name of the character.

`https://swapi.co/api/people/<number>/`

## Add Router (20pts)

Use React Router to create a React/Single Page Application with three pages/Routes. 

Add `react-router` to your project. 

Create three routes to display each of the three components you created in the earlier steps: 

- Home
- Clicker
- StarWars

**Create a link for each of these routes.**

I should be able to click my way to each of the components.

### Extra Credit - Display planets and starships

The Star Wars API (SWAPI) can display information about people, planets, or starships. 

- people - `https://swapi.co/api/people/1/`
- planets - `https://swapi.co/api/planets/1/`
- starships - `https://swapi.co/api/starships/1/`

Your goal is to create a menu that offers these options. You can use: 

```html
<select>
  <option>people</select>
  <option>planets</select>
  <option>starships</select>
</select>
```

You'll need to connect this to state using the controlled component pattern. 

When making a request you should get the "type" from the menu and the "id" number and put them together to make your request to SWAPI. 

`https://swapi.co/api/<type>/<id>/`

Note: There will be a problem with the data you return since the values returned are different for each type. For example: 

- people
  - name
  - height 
  - mass 
  - hair_color
- planets 
  - name 
  - diameter
  - gravity
  - climate
- starships
  - name 
  - model 
  - model
  - cost_in_credits

Solve the problem of displaying data for different types.

### Extra Credit - Displaying more information (10pts)

In the StarWars component, besides the name, display the information listed below:  

- Height
- Mass 
- Hair Color
- Eye Color

### Extra Credit - Error Checking (10pts)

Check for errors in the StarWars component.  

Some values sent to the SWAPI will return an error. For example: `https://swapi.co/api/people/999/` returns 404.

Modify your StarWars Component so it handles errors with an appropriate message.

### Extra Credit - Displaying lists (15pts)

The Star Wars API returns several items that are arrays of links to more data. 

In the StarWars component display some lists. The keys: films, vehicles, and starships contain urls. Display these as a list of anchor tags where the text content is the url value and the href is the same value. 

Display a list of films **(5pts)**

Display a list of vehicles **(5pts)**

Display a list of Starships **(5pts)**

### Extra Credit - Increasing the Count (5pts)

After every ten clicks the amount that clicker increments should double. For example: 

- 1, 2, ..., 9, 10, 12, 14, ..., 18, 20, 24, 28 etc. 

## Extra Credit - Map, Filter, Reduce (15pts)

**Map (5pts)**

Using the data below use map to convert the objects in the array into a strings that read: "`<name> <price> * <qty>`"
	
**Filter (5pts)**
	
Use filter to display all of the item with a qty of 0. 

**Reduce (5pts)**

Use Reduce to calculate the total cost of all items. The cost of each purchase is qty * price.

```JavaScript
[{
  "name": "Ice Cream Bar - Rolo Cone",
  "price": 5.19,
  "qty": 6
}, {
  "name": "Southern Comfort",
  "price": 7.16,
  "qty": 0
}, {
  "name": "Fib N9 - Prague Powder",
  "price": 3.79,
  "qty": 2
}, {
  "name": "Sea Urchin",
  "price": 1.73,
  "qty": 2
}, {
  "name": "Oil - Pumpkinseed",
  "price": 5.1,
  "qty": 2
}, {
  "name": "Sauce - Fish 25 Ozf Bottle",
  "price": 9.75,
  "qty": 0
}, {
  "name": "Tomatoes - Cherry",
  "price": 1.89,
  "qty": 3
}]
```

## Extra Credit - Redux (30pts)

Set up as much of Redux as you can. Use this to handle the Cookie Clicker. I'll give you points for as much of this as you set up. 

- Import dependencies (5pts)
	- redux
	- react-redux
- Actions (5pts)
	- Define an INCREMENT action
	- Define an increment action creator
- Reducers (5pts)
	- Define a clickerReducer
	- Define a root reducer (use combineReducers redux)
- Store (5pts)
	- define store (createStore redux) 
- Provider (5pts)
	- Define the Provider (react-redux)
- Connect a component (5pts)
	- Map State to Props
	- Map Dispatch to props
	- connect (react-redux)

## Total 155pts
