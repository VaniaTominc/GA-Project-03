OVERVIEW

Pistis Trust, a TrustPilot inspired app, is an app where customers can share their experiences about Greek Gods and where Greek Gods can promote their own brand/business. Customers and Gods can register, and while customers can only post their comments and rank their experiences, Gods can also create their own “business” sub-sites. 

Timeframe

9 days.

Demo version

/ 

Deployed version

https://pistis-trust.herokuapp.com/ 

To explore the app, use these login credentials:
Email: admin@email.com
Password: pass

TEAM MEMBERS

Richard Knight: https://github.com/RichardKnight88,
Adrian Pantea: https://github.com/adrianp2021,
Vania Tominc (me): https://github.com/VaniaTominc.

TABLE OF CONTENTS
Brief
Timeframe
Technologies used
Frontend
Backend
Development tools
Installation
Process
Planning
Concept
Organisation
Backend
Setup
Frontend
Components
Styling
Project walkthrough
Bugs, blockers, wins
Extra features and key learnings
Extra features
Key learnings

BRIEF

Build a full-stack application by making your own backend and your own front-end.
Use an Express API to serve your data from a Mongo database.
Consume your API with a separate front-end built with React.
Be a complete product which most likely means multiple relationships and CRUD functionality for at least a couple of models.
Implement thoughtful user stories/wireframes that are significant enough to help you know which features are core MVP and which you can cut.
Have a visually impressive design to kick your portfolio up a notch and have something to wow future clients & employers.
Be deployed online so it's publicly accessible.

TECHNOLOGIES USED

Frontend:

React.js,
Axios,
Semantic UI React,
Bulma,
SASS,
CSS3.

Backend:

Node.js,
MongoDB,
Mongoose,
Express,
React Router DOM,
Bcrypt,
JsonWebToken.



Development tools:

Visual Studio Code,
Insomnia,
Yarn,
Git (branching) & GitHub,
Google Chrome development tools,
Trello board for planning,
Adobe Photoshop (for images),
Zoom,
Slack,
Heroku (deployment).

INSTALLATION

Clone or download GA-Project-03.



Inside your Terminal move to your desired folder and use command.



Run these in Terminal:

mongod --dbpath ~/data/db to run Mongo.

Open the project and open a terminal inside your chosen code editor. 

In terminal type gco development > gco main > git merge development. 

Split terminal in two windows: 

Use 1st terminal for back-end and type:
yarn to install yarn package,
yarn seed to seed database,
yarn serve to run server.
Use 2nd terminal for front-end by typing client and type:
yarn && yarn start. First command will install yarn package, the second command will start front-end server.

 

Go to localhost:3000 in the browser to see the app.

PROCESS

Planning

Concept

The idea for the project came to us as we discussed our interests and began to think about a theme for our project. Because we all love history, especially Greek mythology, we wanted to create a page dedicated to Greek Gods. Since there are already many similar websites on the Internet, we wanted to create our app uniquely, with added functionality. We thought it would be a cool challenge to build a clone of TrustPilot where users could share their experiences about Greek deities, while Greek deities could promote their own brand/business. Even the name of our app, the Pistis Trust, was inspired by Greek mythology. Pistis was the personification of good faith, trust, and reliability. We thought this was an excellent name for our website.

Trello organisation

Because there were so many functionalities on the back-end and components on the front-end that we wanted to implement in our project, but only three of us, we decided to use Trello to organize the project into smaller sections. We decided to set the back-end together, and then do the front-end separately, to maximize our time, by delegating different components to each group member. As the timeframe was short, and we knew the project was the biggest we’d done yet, we met up on Zoom each day from beginning to end, and we were just a call away if someone needed extra help to solve the potential coding issue. We also used Slack to send ideas, or warnings, if two people worked independently on the same component to prevent potential merging conflicts.



Backend

Setup

We created our back-end together so that there was no confusion about any models and databases, but also to consolidate the concepts that we learned in our lectures. This was a splendid idea, because by working together we made the process of setting up the back-end less complicated and managed to do it in record time.

To be able to achieve this, we used VSCode live share where one of us was typing. By using this approach of coding, we could also discover quicker whether there was anything missing in the code that maybe the person typing has missed. All in all, it made our coding process smoother and less error-prone.

Seeding data in our database

In terms of our API, we tried to find an API that could meet our criteria online. We wanted an API that would have more comprehensive detail for each Greek God, including description, familiar relationship, their powers, etc. This proved to be a huge challenge. Most of the APIs we found online were not working or abandoned. For the latter, I am not even surprised, because if you do a Google search about Greek mythology, you can see there are hundreds and hundreds of different deities in Greek mythology. There was nothing to do, but to build our database. Google, Wikipedia, and some other websites became my best friends for finding any data about Greek Gods.

Models, Views, Controllers and middlewares

Knowing we had the data to support our app, we moved on to designing our Models. We created two main schemas: one for Gods and one for users.

godsSchema has an embedded commentsSchema.




In contrast, userSchema additionally checks if a person registering is a God or just a customer.


 
If a customer is a God, he/she/they have all the right to create their sub-site. Meanwhile, a regular customer doesn’t have this right and can only leave a comment.

We also decided which endpoints we would need (views) and which controller / request type (GET, PUT, POST, DELETE) each of them would handle.

The last thing we had to do was to add middlewares: a secureRoute which gives permission to certain endpoints (i.e., customers can only edit/delete comments they have created themselves), but also deusRoute where only Gods have certain privileges like posting, editing or deleting their sub-sites.  



We double-checked all our routes in Insomnia, to ensure that we could log in, register, and check the authentication permissions using token authorization. All tests were successful. All in all, the back-end setup went smoothly.



Frontend

Components

Once we understood which pages we would have on our front-end, we discussed who would do which React component. This does not mean everyone focused only on their component. Since we were in three, we have been aware that if we wanted to build as much as possible into the front-end, we would have to work in pairs or all of us together to maximize time as much as possible. It happened several times when someone began to build a component that was then taken over by another team member, who then finished building it.

I initially started building navbar, a God’s business profile page, and posting, editing, and deleting comments. Throughout the week, I have created our database. As we began to run out of time two days before the end, I decided to help Adrian with his components. As Adrian felt more comfortable with the styling, he took it upon himself to style his components, while I focused more on implementing the functions within those components. In this way, I also built most functions within the registration, login, and post, edit, delete Gods. If I encountered some problems, Richard gave me a hand, and we solved the problems together.

Navbar

The Navbar was quickly set up, but there were some problems when it came to styling. Bulma and React Semantic UI, two of the CSS frameworks we were using for our project, share many classNames which can cause problems when you are trying to use only one of them. Originally, I wanted to use React Semantic UI, but Bulma overwrote my styling. In the end, I decided to use only Bulma.

Navbar changes its appearance depending on the screen size. If the screen is smaller than 1024px, the text hides inside the so-called burger icon and only appears if you click on the icon.




Navbar is visible in all components, except the landing page and the create-god component. Richard added this feature.



God’s business profile page

GodsInfoPage component is intended for the presentation of business, a.k.a representation of a God. When we built the back-end, we didn’t want to call the Gods by IDs, but by their names. When I called API, I thus called an individual God according to his name:



All the data of a God is then displayed on this page. Among other things, their specialization, the place of residence, an external website. Their external website leads to Wikipedia. For fun, I wrote a small function in which the domain of a God's website changes according to gender:



Comments – CRUD

Comments also appear on a God’s business sub-site. The user who wants to write a comment must log in. Only the owner of the comment can edit or delete it.



When writing a comment, the user is expected to write the title and main text and rate the experience. A particular challenge for me was the rating system. The customer determines his rating by clicking on the stars. For the stars, I used the Rating from the React Semantic UI. While I could simply solve the text and title of the text with:




The same could not be achieved for the rating system. The above function was not working. I resorted to googling where several people on StackOverFlow said that with the React Semantic UI, it would be impossible to get a rating value from clicking on the stars. Conditionally, it was possible, but the code was too complex. However, because I am headstrong by nature, I wanted to find my solution. In the end, I managed to do it more simply.




I also used similar logic in a separate component EditComment, where the customer can update or delete his comment. Again, the comment can only be updated or deleted by its owner.



Register

I worked with Adrian on this component. While he devoted himself to designing the website, I began to implement the functions on this website. Because we did not want to write two separate components for the registration of the customer and the registration of a God, we did it within one component. 

After consulting Richard, we found a unique solution to our problem. Namely, Richard suggested we could solve our problem by checking the location from which the person wishing to register comes.



If a person comes from a page dedicated to registering a God, the value of isDeusUser changes from false to true.



Login

Adrian also started building this component. I only helped him with the implementation of the functions. The login page is the same for both the customer and a God. Additionally, one of the functions checks if the person who wants to log in is in the database.



Post / edit / delete Gods

Once a God is registered, he is redirected to the page on which he can create his page.



A God can access edit / delete his page either from his profile page or directly from his GodsInfoPage. When he updates his data, he can also change his logo. The original logo is only a placeholder image because originally there was a plan to add the functionality where a God can upload his logo when creating his page.

Styling

For the third project, we decided to use React Semantic UI in addition to Bulma. We wanted to challenge ourselves and try to use a CSS framework we had not used before. Looking back, it was an amusing experience. Both frameworks use similar names, and it often happened that the final result was not the one we tried to achieve. Also, Bulma and React Semantic UI caused problems if we wanted to use our CSS. Otherwise, we were fortunate to work on the styling from the beginning, and we could solve the problems caused by CSS frameworks during the project week.

There was significant CSS involved, which made it more complex and messy. Instead of working in separate SCSS files, we all worked inside of one combined SCSS. A recipe for disaster. Not due to styling, but due to Git. When it came to committing our branches to the development branch, each’s CSS code was overwriting the existing CSS code and, in many cases, deleting code. At one moment, I lost a day and a half of my work. Thankfully, I had a copy of my folder, so I could save some of my code. We realized it would be better if we do commits together and save our CSS code in a separate file if code was deleted. Also, we created separate SCSS files to prevent potential merging conflicts.

Assets

I created all the assets shown below using Adobe Photoshop. I found all the images on the internet. 

ADD ALL IMAGES.

App walkthrough























BUGS, CHALLANGES, WINS

Bugs

When a user registers, he can also do it only with admin@. I definitely need to change this. 

Challenges

Not having enough time to give admin extra rights on the front-end.
Not having enough time to sort the navbar view depending on meeting conditions, like what the user can view while logged in. 
Building database. With so rich Greek mythology, it was impossible to include more Greek Gods than I managed to include at the end. There are hundred and hundred Greek deities and to include all of them it would take months and months to achieve it. 

Wins

Collaborating as a team has been such a pleasure, and I learned so much from my teammates, especially their unique approach to solving problems.
Linking the back-end and front-end for the first time, and tailoring our back-end to meet our front-end needs.
Building our own database.
Going further with React.js and building more complex components.
Managing to implement almost all functions on the front-end that we built on the back-end.

EXTRA FEATURES AND KEY LEARNINGS

Extra features

Forgot to add the website logo, despite already being created with Adobe Photoshop.
Breaking our front-end into more components and reuse them to avoid code repetition.
Making our app more responsive, especially with smaller screens. 
Giving admin the power to edit or delete user’s comments. We managed to do it on the back-end, but we didn’t have enough time to implement it on the front-end.
Adding an option where someone who registers as a God can subsequently enter their details, not solely upon registration. Currently, if a person who has registered as a God does not enter his or her details, he or she cannot do so subsequently. A button inside the profile page should solve this problem. 
Editing, deleting users.
When creating a page, a God can upload a logo or image of his choice.

Key learnings

Working with Git branches.
Planning all our steps which helped deliver our app on time.
Reading documentations whether it was for debugging issues or to use a new CSS framework.
Last, but not least, relearning about Greek mythology. 


