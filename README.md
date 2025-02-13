# General Assembly - Project 03: Pistis Trust.

## Overview

**Pistis Trust**, a TrustPilot inspired app, is an app where customers can share their experiences about Greek Gods and where Greek Gods can promote their own brand/business. Customers and Gods can register, and while customers can only post their comments and rank their experiences, Gods can also create their own “business” sub-sites. 

+ ### Timeframe

9 days.

+ ### Deployed version

https://pistis-trust.herokuapp.com/ 

To explore the app, use these login credentials:
+ Email: admin@email.com
+ Password: pass

<br />

## Team members

+ **Richard Knight:** https://github.com/RichardKnight88,
+ **Adrian Pantea:** https://github.com/adrianp2021,
+ **Vania Tominc (me):** https://github.com/VaniaTominc.

<br />

## Table of contents

+ Brief
+ Technologies used:
   - Frontend,
   - Backend,
   - Development tools.
+ Installation
+ Process
   - Planning:
     + Concept,
     + Organisation.
   - Backend:
     + Setup.
   - Frontend:
     + Components,
     + Styling.
   - Project walkthrough.
+ Bugs, blockers, wins:
   - Bugs,
   - Blockers,
   - Wins.
+ Future features and key learnings:
   - Future features,
   - Key learnings.

<br />

## Brief

+ **Build a full-stack application** by making your own backend and your own frontend.
+ **Use an Express API** to serve your data from a Mongo database.
+ **Consume your API with a separate frontend** built with React.
+ **Be a complete product** which most likely means multiple relationships and CRUD functionality for at least a couple of models.
+ **Implement thoughtful user stories/wireframes** that are significant enough to help you know which features are core MVP and which you can cut.
+ **Have a visually impressive design** to kick your portfolio up a notch and have something to wow future clients & employers.
+ **Be deployed online** so it's publicly accessible.

<br />

## Technologies used

+ **Frontend:**
  - React.js,
  - Axios,
  - Semantic UI React,
  - Bulma,
  - SASS,
  - CSS3.

+ **Backend:**
  - Node.js,
  - MongoDB,
  - Mongoose,
  - Express,
  - React Router DOM,
  - Bcrypt,
  - JsonWebToken.

+ **Development tools:**
  - Visual Studio Code,
  - Insomnia,
  - Yarn,
  - Git (branching) & GitHub,
  - Google Chrome development tools,
  - Trello board for planning,
  - Adobe Photoshop (for images),
  - Zoom,
  - Slack,
  - Heroku (deployment).

## Installation

+ Clone or download **GA-Project-03**.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129613717-1ed9b348-f6e1-4e3f-b439-18223222bce3.png">
</p>


+ Inside your Terminal move to your desired folder and use command:

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129613772-cefffd7a-dbcc-4032-a0d2-eca0c0c82636.png">
</p>


+ Run these in Terminal:

  - ```mongod --dbpath ~/data/db``` to run Mongo.

+ Open the project and open a terminal inside your chosen code editor. 

  - In terminal type ```gco development``` > ```gco main``` > ```git merge development```. 

  - Split terminal in two windows: 

    + Use 1st terminal for backend and type:
      - ```yarn``` to install yarn package,
      - ```yarn seed``` to seed database,
      - ```yarn serve``` to run server.
      
    + Use 2nd terminal for frontend by typing client and type:
      - ```yarn && yarn start```. First command will install yarn package, the second command will start frontend server.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129614154-98dea822-3e26-479d-aa48-f71f599a7dc8.png">
</p>

   + Go to ```localhost:3000``` in the browser to see the app.
<br />

## Process

+ ### Planning

#### ➡️ Concept

The idea for the project came to us as we discussed our interests and began to think about a theme for our project. Because we all love history, especially Greek mythology, we wanted to create a page dedicated to Greek Gods. Since there are already many similar websites on the Internet, we wanted to create our app uniquely, with added functionality. We thought it would be a cool challenge to build a clone of TrustPilot where users could share their experiences about Greek deities, while Greek deities could promote their own brand/business. Even the name of our app, the Pistis Trust, was inspired by Greek mythology. Pistis was the personification of good faith, trust, and reliability. We thought this was an excellent name for our website.

#### ➡️ Trello organisation

Because there were so many functionalities on the backend and components on the 
end that we wanted to implement in our project, but only three of us, we decided to use Trello to organize the project into smaller sections. We decided to set the backend together, and then do the frontend separately, to maximize our time, by delegating different components to each group member. As the timeframe was short, and we knew the project was the biggest we’d done yet, we met up on Zoom each day from beginning to end, and we were just a call away if someone needed extra help to solve the potential coding issue. We also used Slack to send ideas, or warnings, if two people worked independently on the same component to prevent potential merging conflicts.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617327-5bc60c1a-ffc1-4493-b9fc-2878959701b9.png">
</p>

+ ### Backend

#### ➡️ Setup

We created our backend together so that there was no confusion about any models and databases, but also to consolidate the concepts that we learned in our lectures. This was a splendid idea, because by working together we made the process of setting up the backend less complicated and managed to do it in record time.

To be able to achieve this, we used VSCode live share where one of us was typing. By using this approach of coding, we could also discover quicker whether there was anything missing in the code that maybe the person typing has missed. All in all, it made our coding process smoother and less error-prone.

#### ➡️ Seeding data in our database

In terms of our API, we tried to find an API that could meet our criteria online. We wanted an API that would have more comprehensive detail for each Greek God, including description, familiar relationship, their powers, etc. This proved to be a huge challenge. Most of the APIs we found online were not working or abandoned. For the latter, I am not even surprised, because if you do a Google search about Greek mythology, you can see there are hundreds and hundreds of different deities in Greek mythology. There was nothing to do, but to build our database. Google, Wikipedia, and some other websites became my best friends for finding any data about Greek Gods.

#### ➡️ Models, Views, Controllers and middlewares

Knowing we had the data to support our app, we moved on to designing our Models. We created two main schemas: one for Gods and one for users.

```godsSchema``` has an embedded ```commentsSchema```.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617460-dcf36de0-a272-430e-823f-183808d46963.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617472-fbff134c-3e9b-43d1-be1c-dfe62784f5f0.png">
</p>

In contrast, ```userSchema``` additionally checks if a person registering is a God or just a customer.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617494-16f071f1-9f99-4c7d-b05f-a61288fb52d3.png">
</p>
 
If a customer is a God, he/she/they have all the right to create their sub-site. Meanwhile, a regular customer doesn’t have this right and can only leave a comment.

We also decided which endpoints we would need (views) and which controller / request type (`GET`, `PUT`, `POST`, `DELETE`) each of them would handle.

The last thing we had to do was to add middlewares: a ```secureRoute``` which gives permission to certain endpoints (i.e., customers can only edit/delete comments they have created themselves), but also ```deusRoute``` where only Gods have certain privileges like posting, editing or deleting their sub-sites.  

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617585-90d1633d-4393-43c7-acb0-923851ae2d7d.png">
</p>

We double-checked all our routes in Insomnia, to ensure that we could log in, register, and check the authentication permissions using token authorization. All tests were successful. All in all, the backend setup went smoothly.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129617604-117baba5-2ef4-4c0b-afda-bd8427e9acbc.png">
</p>

+ ### Frontend

#### ➡️ Components

Once we understood which pages we would have on our frontend, we discussed who would do which React component. This does not mean everyone focused only on their component. Since we were in a group of three, we have been aware that if we wanted to build as much as possible into the frontend, we would have to work in pairs or all of us together to maximize time as much as possible. It happened several times when someone began to build a component that was then taken over by another team member, who then finished building it.

I initially started building navbar, a God’s business profile page, and posting, editing, and deleting comments. Throughout the week, I have created our database. As we began to run out of time two days before the end, I decided to help Adrian with his components. As Adrian felt more comfortable with the styling, he took it upon himself to style his components, while I focused more on implementing the functions within those components. In this way, I also built most functions within the registration, login, and post, edit, delete Gods. If I encountered some problems, Richard gave me a hand, and we solved the problems together.

   - #### Navbar
   
The ```Navbar``` was quickly set up, but there were some problems when it came to styling. Bulma and React Semantic UI, two of the CSS frameworks we were using for our project, share many classNames which can cause problems when you are trying to use only one of them. Originally, I wanted to use React Semantic UI, but Bulma overwrote my styling. In the end, I decided to use only Bulma.

Navbar changes its appearance depending on the screen size. If the screen is smaller than 1024px, the text hides inside the so-called burger icon and only appears if you click on the icon.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618127-4b62a814-f88b-4f70-915f-f8504005eef4.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618148-1e011b35-7602-41e4-8889-5aa9be6f980c.png">
</p>

Navbar is visible in all components, except the landing page and the create-god component. Richard added this feature.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618185-55b4f049-0960-4715-abb0-52b7e2bc5269.png">
</p>

   - #### God’s business profile page

```GodsInfoPage``` component is intended for the presentation of business, a.k.a representation of a God. When we built the backend, we didn’t want to call the Gods by IDs, but by their names. When I called API, I thus called an individual God according to his name:

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618238-927aa65f-b868-4737-98c7-5da19b30d672.png">
</p>

All the data of a God is then displayed on this page. Among other things, their specialization, the place of residence, an external website. Their external website leads to Wikipedia. For fun, I wrote a small function in which the domain of a God's website changes according to gender:

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618251-c63e387c-1673-40cf-b951-f5ba3ca33b45.png">
</p>

   - #### Comments – CRUD

```Comments``` also appear on a God’s business sub-site. The user who wants to write a comment must log in. Only the owner of the comment can edit or delete it.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618309-f2ecca79-bf2a-44f0-9bc2-a8280c8c2d62.png">
</p>

When writing a comment, the user is expected to write the title and main text and rate the experience. A particular challenge for me was the rating system. The customer determines his rating by clicking on the stars. For the stars, I used the Rating from the React Semantic UI. While I could simply solve the text and title of the text with:

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618338-abdb8f08-b8a6-4fc1-ad37-a29ec6480bba.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618364-f392f861-373e-44ea-a029-21f64e578347.png">
</p>

The same could not be achieved for the rating system. The above function was not working. I resorted to googling where several people on StackOverFlow said that with the React Semantic UI, it would be impossible to get a rating value from clicking on the stars. Conditionally, it was possible, but the code was too complex. However, because I am headstrong by nature, I wanted to find my solution. In the end, I managed to do it more simply.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618406-2b8f2ec3-bbf8-4abe-90f8-8cc63ef9e324.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618430-c84c43ec-eeeb-4317-ba79-8df6c95ca78a.png">
</p>

I also used similar logic in a separate component ```EditComment```, where the customer can update or delete his comment. Again, the comment can only be updated or deleted by its owner.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618482-7ac1c2a1-c5be-41c8-9b9e-f94cbf4bc088.png">
</p>

   - #### Register

I worked with Adrian on this component. While he devoted himself to designing the website, I began to implement the functions on this website. Because we did not want to write two separate components for the registration of the customer and the registration of a God, we did it within one component. 

After consulting Richard, we found a unique solution to our problem. Namely, Richard suggested we could solve our problem by checking the location from which the person wishing to register comes.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618533-e10e3222-eb5c-4592-9cc6-cdf64df2e053.png">
</p>

If a person comes from a page dedicated to registering a God, the value of ```isDeusUser``` changes from false to true.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618572-61ccd160-89d6-49bd-96d5-cd99f3b579f0.png">
</p>

   - #### Login

Adrian also started building this component. I only helped him with the implementation of the functions. The login page is the same for both the customer and a God. Additionally, one of the functions checks if the person who wants to log in is in the database.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618601-6043da91-50a4-4433-b6f0-a9ccb2b1d1b6.png">
</p>

   - #### Post / edit / delete Gods

Once a God is registered, he is redirected to the page on which he can create his page.

<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618644-15dd45b8-3af3-47ad-abf4-616eff8d1a7e.png">
</p>

A God can access edit / delete his page either from his profile page or directly from his ```GodsInfoPage```. When he updates his data, he can also change his logo. The original logo is only a placeholder image because originally there was a plan to add the functionality where a God can upload his logo when creating his page.

#### ➡️ Styling

For the third project, we decided to use React Semantic UI in addition to Bulma. We wanted to challenge ourselves and try to use a CSS framework we had not used before. Looking back, it was an amusing experience. Both frameworks use similar names, and it often happened that the final result was not the one we tried to achieve. Also, Bulma and React Semantic UI caused problems if we wanted to use our CSS. Otherwise, we were fortunate to work on the styling from the beginning, and we could solve the problems caused by CSS frameworks during the project week.

There was significant CSS involved, which made it more complex and messy. Instead of working in separate SCSS files, we all worked inside of one combined SCSS. A recipe for disaster. Not due to styling, but due to Git. When it came to committing our branches to the development branch, each’s CSS code was overwriting the existing CSS code and, in many cases, deleting code. At one moment, I lost a day and a half of my work. Thankfully, I had a copy of my folder, so I could save some of my code. We realized it would be better if we do commits together and save our CSS code in a separate file if code was deleted. Also, we created separate SCSS files to prevent potential merging conflicts.

   - #### Assets

I created all the assets shown below using Adobe Photoshop. I found all the images on the internet. 

<p align="center">
  <img src="https://i.ibb.co/G0Sr2Jx/Apollo-Cube.png" width="300">
  <img src="https://i.ibb.co/3CbNJmd/AresCube.png" width="300">
  <img src="https://i.ibb.co/chb1L0D/Athena-Cube.png" width="300">
  <img src="https://i.ibb.co/BnjWCzH/HadesPSD.png" width="300">
  <img src="https://i.ibb.co/DQKJzBv/Poseidon-Cube.png" width="300">
  <img src="https://i.ibb.co/p2XfVzj/ZeusCube.png" width="300">
</p>

<p align="center">
  <img src="https://i.ibb.co/878JXTf/Logo-Image.png" width="300">
  <img src="https://i.ibb.co/hDM7Sh7/demeter-horn-logo.png" width="300">
</p>

<p align="center">
  <img src="https://i.ibb.co/NS1SJRd/hero-cracked-marble.jpg" width="500">
  <img src="https://i.ibb.co/ZcTNSb9/marble-Background.png" width="500">
</p>

#### ➡️ App walkthrough


<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618954-532843f7-651c-4eae-a863-818e73c7af82.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618963-4a55788e-ea6a-434b-9d5f-5f1fc47f7c8f.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618971-9dba6d77-cabf-4f4b-871a-5b59758e4e6a.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618983-a1cd1377-58c9-497a-b1db-cf8d791adfec.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129618994-78766984-7ff6-4344-b4e7-0e0f0ef744ab.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619004-cb8a484a-352a-4941-a278-76e0772a5f46.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619048-7b1981c2-8513-4d5a-a463-5cec15a398a1.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619093-42b30c06-ba5a-4308-b571-27b42f3de11f.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619111-cb100ca5-93a9-4c6d-8682-994f818e2b77.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619138-a367a814-274c-4678-a538-54fb17bbb57e.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619164-ebf534f7-563c-4e20-a9a7-099307b49d83.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619190-958e1c9d-eafd-4ee8-b1f2-2896654c0a5f.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619214-74c472ce-9795-45fd-b586-4cfaa75ee9cc.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619234-af4c67ea-61cd-4fc5-b15f-1296bdf42b32.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619257-92a036c3-45a8-4659-884f-165ef7f919ec.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619280-b2973a6f-4afa-4794-b45d-30a6afc4bb83.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619306-c916b9ab-4399-4535-bed5-ba0535e54060.png" width="800">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/83227280/129619329-8ae33002-2bc7-4b24-a918-c351ff407084.png" width="800">
</p>

<br />

## Bugs, challenges, wins

+ ### Bugs

   - When a user registers, he can only do this with admin@, I definitely need to change this

+ ### Challenges

   - Not having enough time to give admin extra rights on the frontend.
   - Not having enough time to sort the navbar view depending on meeting conditions, like what the user can view while logged in. 
   - Building the database. With so much rich Greek mythology, it was impossible to include more Gods than I have already added in the time frame. There are hundreds and hundreds of Greek deities and to include all of them would take months to achieve.

+ ### Wins

   - Collaborating as a team has been such a pleasure, and I learned so much from my teammates, especially their unique approach to solving problems.
   - Linking the backend and frontend for the first time, and tailoring our backend to meet our frontend needs.
   - Building our own database.
   - Going further with React.js and building more complex components.
   - Managing to implement almost all functions on the frontend that we built on the backend.

<br />

## Future features and Key learnings

+ ### Future features

   - Forgot to add the website logo, despite already being created with Adobe Photoshop.
   - Breaking our frontend into more components and reuse them to avoid code repetition.
   - Making our app more responsive, especially with smaller screens. 
   - Giving admin the power to edit or delete user’s comments. We managed to do it on the backend, but we didn’t have enough time to implement it on the frontend.
   - Adding an option where someone who registers as a God can subsequently enter their details, not solely upon registration. Currently, if a person who has registered as a God does not enter his or her details, he or she cannot do so subsequently. A button inside the profile page should solve this problem. 
   - Editing, deleting users.
   - When creating a page, a God can upload a logo or image of his choice.

+ ### Key learnings

   - Working with Git branches.
   - Planning all our steps which helped deliver our app on time.
   - Reading documentations whether it was for debugging issues or to use a new CSS framework.
   - Last, but not least, relearning about Greek mythology. 


