# Countdown Application 

A simple project designed to get Web-Developers comfortable with the syntax and style of writing in React.

Concepts reviewed in the making of this project: 

** A component in React is an independent and reusable piece of UI. 

** Styling divs in App.jsx uses "className" as opposed to "class" 

** Introduction to State and Reactivity: 

Each component has its own local state, with respect to the global state of the entire app 
Just like in a school, 
It has a state of its number of students, teachers, classrooms, and etc.
Each student has its own state: number of textbooks, pens, etc. 

** Initializing and declaring state within a component:  

** Updating state dynamically: 

** Passing state from parent component (App) to child component (<Clock/> will store the values of state from the parent in the props object in the child component. 

## License & Copyright 
---
© David Katz Software Engineer - Coding Instructor
https://www.skillshare.com/user/dtkatz

---



React runs on JavaScript and React Code follows ES6 (EcmaScript) 

Redux: 
Allows to build applications that scale. 

Review

A component in React is an independent and reusable piece of UI. 
JSX looks just like HTML or XML but is actually JavaScript and allows us to create react components. 
    // ES6 classes were introduced in 2015 to allow us to write JavaScript in an Object-
    // oriented model. 


import React, {Component} from 'react';
Importing React, {Component} from ‘react’

App extends Component syntax: 
class App extends Component {
    
    render(){
        return(
        <div>Countdown Champ, App Component</div>
        )
    }
}

Importing App.css into the application looks like this: 
import './App.css';
 
class App extends Component {
 
    render(){
        return(
        <div className="App">
 
------------------------------------------------------------------------------------------------------------------------------
.App {
    text-align: center;
    font-size: 35px; 
    margin-top: 20%;
}
------------------------------------------------------------------------------------------------------------------------------

Styling divs in App.jsx 
            <div className="App-title">Countdown to December 25, 2017</div>
            <div>
                <div className="Clock-days">14 Days</div>
                <div className="Clock-hours">30 hours</div>
                <div className="Clock-minutes">15 minutes </div>
                <div className="Clock-seconds">20 seconds</div>
            </div>
            <div>
                <input placeholder="new date"/>
------------------------------------------------------------------------------------------------------------------------------

Introduction to State and Reactivity 

Each component has its own local state, with respect to the global state of the entire app 

Just like in a school, 
It has a state of its number of students, teachers, classrooms, and etc.
Each student has its own state: number of textbooks, pens, etc. 

------------------------------------------------------------------------------------------------------------------------------

Creating and declaring state within a component: 

class App extends Component {
    constructor(props){
        super(props);
        // In React, state is always an object 
        this.state = {
            deadline: 'December 25, 2017'
        }
    }

Applying it to our application and changing static plain HTML data:
   <div className="App-title">Countdown to {this.state.deadline}</div>

------------------------------------------------------------------------------------------------------------------------------

Updating state dynamically: 
// You must never mutate or change state directly.
        this.state.deadline = 'November 25, 2017'
        // this will cause the component to not render. 
        // Instead, we use the this.setState() method 


We create a method called “changeDeadline()” that utilizes the “this.setState” build in method in components 

Then we add an event listener to the button to wait until it is clicked to call our method. 
                <button onClick={()=> this.changeDeadline()}>Submit</button>

------------------------------------------------------------------------------------------------------------------------------

        this.state = {
            deadline: 'December 25, 2017',
            newDeadline: ''

Capture the input when the user changes the value of the input element. 
Demonstration of capturing the value of the change 
                <input placeholder="new date"
                onChange={event=> console.log('event', event.target.value)}
                />

<input placeholder="new date"
                onChange={event=> this.setState({newDeadline: event.target.value})}
                />
onChange, call the setState method on this component to set the new Deadline to the users’ input

------------------------------------------------------------------------------------------------------------------------------
Passing state from parent component (App) to child component (<Clock/> 
            <Clock
            deadline={this.state.deadline}
Which has the values of App.state stored into the Clock’s props. 
        console.log('this.props', this.props)
        console.log('this.state', this.state)

Clock.jsx:14 this.props {deadline: "December 25, 2017"}
Clock.jsx:15 this.state {days: 0, hours: 0, minutes: 0, seconds: 0}



        const time = Date.parse(deadline) - Date.parse(new Date());

