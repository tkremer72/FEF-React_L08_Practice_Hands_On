# L08 Practice Hands On

# Component Lifecycle

Lesson 8 Practice Hands-On
Directions
For your Lesson 8 Practice Hands-On, you will be working within a project provided below. This Hands-On will not be graded, but we encourage you to complete it. The best way to become a great programmer is to practice! Once you have submitted your project, you will be able to access the solution on the next page.

Setup
Start off by downloading the starter project and unzipping it. The starter project will be in a folder named React.

Starter Project

After unzipping, move the starter project folder to the FEFReact folder located inside the FullStackWeb folder and rename it from React to L08HandsOn.

Open up your terminal/command prompt.

Run the following to navigate to your Desktop

cd Desktop
Next, navigate to the FullStackWeb directory in your terminal.

cd FullStackWeb
Then, navigate to the FEFReact directory in your terminal.

cd FEFReact
Navigate into the L08HandsOn directory:

cd L08HandsOn
Now that you are in the L08HandsOn directory, run the following:

npm install
Once npm has finished installing, you can test that the server is working with the following command:

npm start
You should now see your browser open up a blank page with an alert box saying "It's alive!".

Tip!
You can stop this process by pressing Control + C in the terminal, but for now, keep the server running.

Add the necessary import statements at the top of the src/index.js file and remove the alert that currently lives in that file:

import React from 'react';
import { render } from 'react-dom';
Requirements
Add the code for the following requirements within the src/index.js file:

Modify the List component to include shouldComponentUpdate so that when duplicate props are provided, the component does not re-render.

Currently, you can use the 1 and 2 keys on your keyboard to change the props being passed into the List. Pressing the same key multiple times re-renders the page but after you add shouldComponentUpdate, it shouldn't.
class List extends React.Component {
    render() {
        console.log("List's render function"); // this should not be logged multiple times if the exact same props are provided a second time
    const list = this.props.items.map(item => (<li key={item}>{item}</li>));

    return (
        <ul>
            {list}
        </ul>
    );
    }
}

const list1Items = ['Eggs', 'Bread', 'Artisan cheese'];
const list2Items = ['Trains', 'Planes', 'Automobiles'];

const renderItems = (items) => {
    render(
    <List items={items} />,
    document.getElementById('root')
    );
}

document.addEventListener('keydown', event => {
    // this checks if the 1 key is pressed
    if (event.code === 'Digit1') {
        renderItems(list1Items);
    }
    // this checks if the 2 key is pressed
    else if (event.code === 'Digit2') {
        renderItems(list2Items);
    }
});

renderItems(list1Items);