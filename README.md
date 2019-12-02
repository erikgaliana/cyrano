# CyranoApp



## Description

Cyrano is a social network where you can find love quotes. Users can like the quotes in order to make a top chart quotes, add their favorites to their profile and add their own quotes to the web page so that other users can like it.



## User Stories

- **404** - As a user I want to see a nice 404 page when I go to a page that doesn’t exist so that I know it was my fault
- **500** - As a user I want to see a nice error page when the super team screws it up so that I know that is not my fault
- **landing** - As a user I want to be able to access the landing page and login/sign up
- **sign up** - As a user I want to sign up on the web page so that I can find and add quotes
- **login** - As a user I want to be able to log in on the web page so that I can get back to my account
- **logout** - As a user I want to be able to log out from the web page so that I can make sure no one will access my account
- **public feed** - As a user I want to see the top rated quotes and random quotes.
- **like quotes** - As a user I want to be able to like quotes
- **favorite quotes** - As a user I want to be able to add my favorite quotes to my profile
- **add quote** - As a user I want to be able to add quotes to the web page
- **edit profile** - As a user I want to be able to edit my profile
- **profile** - As a user I want to see my quotes and my favorite quotes in my profile



## API Routes (Back-end):



| **Method** | **Route**             | **Description**                                              | Request  - Body                          |
| ---------- | :-------------------- | ------------------------------------------------------------ | ---------------------------------------- |
| `GET`      | `/`                   | Main page route.  Renders landing `index` view.              |                                          |
| `GET`      | `/login`              | Renders `login` form view.                                   |                                          |
| `POST`     | `/login`              | Sends Login form data to the server.                         | { username, password}                    |
| `GET`      | `/signup`             | Renders `signup` form view.                                  |                                          |
| `POST`     | `/signup`             | Sends Sign Up info to the server and creates user in the DB. | { username, password, bio, email, photo} |
| `GET`      | `/user/home`          | Private route. Renders `home` view.                          |                                          |
| `GET`      | `/user/home/random`   | Private route. Renders `home/random` view with random quotes |                                          |
| `GET`      | `/user/add`           | Private route. Renders the `add` view.                       |                                          |
| `POST`     | `/user/add`           | Private route. Sends Quote info to the server and creates the quote in the db. Redirects to `profile` view. | { text, author }                         |
| `GET`      | `/user/profile/`      | Private route. Renders `profile` view with "my quotes" and "favourite" quotes. |                                          |
| `DELETE`   | `/user/profile/`      | Private route. Deletes quote of a user's id quote and redirects to `profile` | { _id }                                  |
| `GET`      | `/user/edit-profile/` | Private route. Renders `edit-profile` view.                  |                                          |
| `POST`     | `/user/edit-profile/` | Private route. Sends User info to the server and updates the user in the db. Redirects to `profile` view. | { username, password, bio, email, photo} |



## Models

User model

```javascript
{
  username: String,
  email: String,
  password: String,
  photo: String,
  bio: String,
  quotes: [quoteId],
  favorites: [quoteId],
  liked: [quoteId],  
}

```



Quote model

```javascript
{
  text: String,
  author: userId,
  likes: [userId],
  lagnuage: String,
  type: String
}

```



## Project structure

```
starter-code/
├── .gitignore
├── app.js
├── bin
│   └── www
├── models
│   ├── quote.js
│   └── user.js
├── package.json
├── public
│   ├── icons
│   └── stylesheets
│       └── style.scss
├── routes
│   ├── index.js
│   ├── login.js
│   ├── signup.js
│   ├── logout.js
│   ├── user.js
│   ├── user-edit.js
│   └── add.js
└── views
    ├── auth
    │   ├── login.hbs
    │   └── signup.hbs
    ├── error.hbs
    ├── index.hbs
    ├── layouts
    │   ├── layout.hbs
    |		└── user-layout.hbs
    ├── user
    │   ├── home.hbs
    │   ├── random.hbs
    │   ├── add.hbs
    │   ├── profile.hbs
    │   ├── search.hbs
    |		└── edit-profile.hbs

```





## Backlog

[See the Trello board.](https://trello.com/b/Qw9sTj2L/planning)





## Links



### Git

The url to your repository and to your deployed project

[Deploy Link](https://cyrano-app.herokuapp.com/)



<br>



### Slides

The url to your presentation slides

[Slides Link](https://docs.google.com/presentation/d/1Frh8japy7cSnuAcvR2Q2peMtav2uDUv8s_auTBW3t88/edit#slide=id.p)
