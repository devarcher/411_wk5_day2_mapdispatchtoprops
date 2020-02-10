

##### Pie Chart & Total

- Now that we have that working we are going to practice what we learned last class and add containers and mapStateToProps function for the `Chart` and `Total` components. Why? Because we want these to always have the current "cars" information. We'll see how this is useful in a second.

- Create a file called `Total.js` underneath the "containers" folder and create a `mapStateToProps` function. You can use the `Car.js` file as an example and simply change the component from "Car" to "Total".

- Next, go to the Dashboard COMPONENT and change the import for "Total" to reference the container instead of the component. Ex. `import Total from './Total'`

- Finally, go to the `Total.js` file and under the components folder and change the number "4" to `{props.cars.length}`. The total should now display "20".

- Go ahead and add and remove items from the table. Notice the total update in real time. This is something that wouldn't have been possible with normal React state because the information for "Total" lives in a different component. Components are meant to be re-usable so if we ever wanted to put this "Total" somewhere else in our application we could just import it and use it like in dashboard and it will always have the correct cars data.

- Now we need to do the same thing for the `Chart` component. Create a file called `Chart.js` under containers and hook up the `mapStateToProps` function so that it has access to the "cars" prop. You can copy from `Total` and change the component names.

- Once agin in Dashboard COMPONENT, change the Chart import so that it points to the container.

- Finally, in `components/Chart.js` above the return statement, create two variables called "over" and "under". Use the "filter" method to filer the "props.cars" for cars who's horsepower match the criteria. Then use those values in the corresponding Pie Chart. They will be "over.length" and "under.length"

- You should see 4 (red) over 200 and 16 (orange) under 200. But wait.. since this data is connected to Redux it will change according to our actions. So go ahead and delete 3 users who's horsepower is under 200. Did you see the chart change? Again, since Dashboard, Chart and Total are all referencing the same data... they will always be in sync. The addition of the Pie Chart will always equal the total.

- One more thing, when you remove a user from the list you can also go to the homepage and notice that it's card has also been removed. Pretty cool, huh? It's all tied together.
