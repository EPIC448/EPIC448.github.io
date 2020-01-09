---
layout: post
title:      "React/Redux /Coding Principles /"
date:       2020-01-08 20:21:04 -0500
permalink:  react_redux_coding_principles
---

# what I learned building out my BlogPost Project with Ruby on Rails Backend and React/Redux 



> “Each of us have looked at something and said: “That looks so easy. . . “ — until we try to do it. We have to work hard to get our thinking clean to make things simple.

 -Alexey Kovtunets ”


We all are aware of acronyms such as KISS, Yagni, Dry.    The issue is most developer never really use this acronyms  when coding.  Then the question becomes how does this relate to the BlogPost Project. 

Starting out this project, I wanted to make it very complex with different moving parts and functions in hopes of impressing whom every use/see the app.  Then, a friend mentions to me, saying “Simplicity is genius”. Often developer such as myself assumes complexity equal genius which is not the case. As a complex App tend to lead more issues than bargained for such as  slower implementation of corrections, challenge to maintain, deficit understanding, and increase risk of bugs just to name a few. So what does this acronym means?


> Kiss 
[](https://thumbs.gfycat.com/ZealousSparklingAmericanwarmblood-small.gif)
   “KISS is an acronym for “Keep it simple, stupid” as a design principle noted by the U.S. Navy in 1960. The KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore simplicity should be a key goal in design and unnecessary complexity should be avoided. The phrase has been associated with aircraft engineer Kelly Johnson. Variations on the phrase include: ‘Keep it simple, silly’, ‘keep it short and simple’, ‘keep it simple and straightforward’, ‘keep it small and simple’ and ‘keep it stupid, simple’.”
— Wikipedia


Any working developer will testify to the Horror of reading a legacy code  that seem impossible.
Figuring out what the function, method, and attribute are doing seem foreign. We often want to provide a more complex, stronger, and alluring solution often at the cost for KISS method. While on the other hand, when this method is implemented,  it make for easy  to maintain code with faster implementation. 

> Yagni
![](http://m.quickmeme.com/img/c8/c8b8b603a9ac0b7dec3a00788dd741806f707ca31831048587608e3f45b1f89d.jpg)
“You aren’t gonna need it” is a principle of extreme programming that states a programmer should not add functionality until deemed necessary. XP co-founder Ron Jeffries has written: “Always implement things when you actually need them, never when you just foresee that you need them.” Other forms of the phrase include “You aren’t going to need it” and “You ain’t gonna need it”.
— Wikipedia


This was a challenge for me. Instead of focusing on the minimum valuable product(MVP) for this project, I literally spent 2 days mapping out what features I want the App to have, and how it need to tap into an API, Bitcoin features, and my need for its to be before it time. The moral of the YAGNI method suggest that no need to  switch careers to be a Fortune teller attempting to forecast what features the app may possibly need in the future. This leading to adding extra layer of complexity to your program that is not even needed.  So yes, I lowered my ego, and kept it as simple as possible . Using  class components and functional components when needed. And worrying less about adding several implementation of states. 

>** Dry**
[](https://paulieweb.com/about/slants/img/skele-dry.gif)
“Don’t repeat yourself (DRY) is a principle of software development aimed at reducing repetition of software patterns, replacing them with abstractions; and several copies of the same data, using data normalization to avoid redundancy.
The DRY principle is stated as “Every piece of knowledge must have a single, unambiguous, authoritative representation within a system”. When the DRY principle is applied successfully, a modification of any single element of a system does not require a change in other logically unrelated elements. Additionally, elements that are logically related all change predictably and uniformly, and are thus kept in sync.”
— Wikipedia


Dry is one of the most fundamental principle in software development. It goal is to help avoid duplication in any part of your program be it functions, code block or method.  It enable  a more cleaner code.  Dry advocates that duplication is a waste , repeating a process need automation, and repetition in logic need abstractions. For this project, this was exhibited when creating the class  form component for this project.  As a sample it looked something like this. 

```


class ParentComponent extends React.Component {
  state = {
    firstName: "",
    lastName: "",
  }
 
  handleChange = event => {
    this.setState({
      [event.target.name]: event.target.value
    })
  }
 
  render() {
    return (
      <div>
        <Form
          formData={this.state}
          handleChange={this.handleChange}
        />
        <DisplayData formData={this.state} />
      </div>
    )
  }
}
 
```
export default ParentComponent;


// src/components/Form
import React from 'react';
 
```
class Form extends React.Component {
  render() {
    return (
      <div>
        <form>
          <input
            type="text"
            name="firstName"
            onChange={event => this.props.handleChange(event)}
            value={this.props.formData.firstName}
          />
          <input
            type="text"
            name="lastName"
            onChange={event => this.props.handleChange(event)}
            value={this.props.formData.lastName} />
        </form>
      </div>
    )
  }
}
 
export default Form
```


Focus: on the handleChange part of the code.  Without adherence to the Dry Principle, That code will look like this.


`handleFirstNameChange = event => {
    this.setState({
      firstName: event.target.value
    })
  }
 
  handleLastNameChange = event => {
    this.setState({
      lastName: event.target.value
`


So as you can see, Dry is very important in code, Else, we will have multiple functions, methods, re-writeing what were already wrote (a.k.a WET) Write Cverything Twice. 



In closing,  the redux react project  can easily be complicated if I made it so. So some take away i will like to share:

* Choosing the a technology  that I understood well is key.
* Set my Ego aside and ask for help with  questions as needed
*  Challenge my logic and ask ” Do you need this feature in your app”
*  And always balancing out the YAGNI, KISS, DRY principles in the back of my mind. 

Just to name a few.
 Techture nation, What are your thought  on the subject. What other principles would you like to add to this list. 

Cheers
Samuel.O

