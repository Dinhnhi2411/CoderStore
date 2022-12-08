# Coder-store-FE

## Background

- MeSpace is a social network that allows people to join by creating accounts. Each User should provide a name, an email and a password to create an account.

- The email address should not link to any account in the system. After joining MySpace, users can update their profile into like Avatar, Company , Job Title, Social Links and a short description about themselves.

- Users can write Posts that contain text content and an image. The new posts will be shown on the user profile page, allowing other users to comment. Users can also React with like or dislike on a post or a Comment

- Users can send Friend Requests to other users who have an open relationship with them. Users can accept or decline a friend request. After accepting a friend request, both become friends and they can see posts of each other

## Authentication

- As a user I can sign in. with my email and password.
- As a user, I can register for a new account, email, password.
- As a user, I can stay signed in with refreshing page.

## Users

- As a user, I can see a list of other users do taht I can send, accept or decline friend requests.
- As a user, I can get my current profile info (stay isgned in after page refresh)
- As a user, I can see the profile of a specific user given a user ID.
- As a user, I can update my profile into like Avatar, Company, Job Title, Social Links and short description.

## Posts

- As a user, I can see a list of posts
- As a user, I can create a new post with text content and an image.
- As a user, I can edit my posts
- As a user, I can delere my posts

## Comments

- As a user, I can see a list of comments on a post
- As a user, I can write comments on a post
- As a user, I can update my comments
- As a user, I can delete my comments

## Reactions

- As a user, I can react like or dislike to a post or a comment

## Friends

- As a user, I can send a friend request to another user who is not my friend.
- As a user, I can see a list of frinds requer I have received
- As a user, I can see a list of my friends.
- As a user, I can accpet or decline a freidn request.
- As a user, I can cancel a friend request I sent
- As a user, I can unfriend a suer in my friend list.

## API endpoints

### Auth APIs

```javascript
- @route POST /auth/login
- @description Log in with username and password
- @body {email, passsword}
- @access Public
```

### Friend APIs

```javascript
- @route GET /friends/requests/incoming
- @description Get the list of received pending requests
- @access Login required
```

```javascript
- @route GET /friends/requests/outgoing
- @description Get the list of sent pending requests
- @access Login required
```

- @route GET /friends/
- @description Get the list of friends
- @access Login required

- @route POST /friends/requests
- @description Send a friend request
- @body {to : User ID}
- @access Login required

- @route PUT /friends/requests/:userId
- @description Accept/Reject a received pending requests
- @body {status : 'accepted' or 'declined'}
- @access Login required

- @route DELETE /friends/requests/:userId
- @description cancel a friend request
- @access Login required

- @route DELETE /friends/:userId
- @description remove a friend
- @access Login required

### User APIs

- @route GET /users/page=1?&limit=10
- @description Get user with pagination
- @body
- @access Login required

- @route GET /users/me
- @description Get current user info
- @body
- @access Login required

- @route GET /users/:id
- @description Get user profile
- @body
- @access LOgin required

- @route POST /users
- @description Register new user
- @body {name, email, password}
- @access Public

- @route PUT /users/:id
- @description Update user profile
- @body {name, avarta,cover,aboutMe,city country, company, jobtitle, fblinl, iglink, linkLink, twiiLink}
- @access Login required

### Post APIs

- @route GET /posts/:id/comments
- @description Get comments of a post
- @body
- @access Login required

- @route GET /posts/:id
- @description Get a single post
- @body
- @access Login required

- @route POST /posts
- @description Create a new post
- @body {content, image}
- @access Login reuqired

- @route PUT /posts/user/userId? page=1&limit=10
- @description Get all posts an user can see with pagination
- @body
- @access Login required

- @route PUT /posts/:id
- @description Update a post
- @body {content, image}
- @access Login required

- @route DELETE /posts/:id
- @description Delete a post
- @body
- @access Login required

### Comment APIs

- @route GET /comments/:id
- @description Get details of a comment
- @body
- @access Login required

- @route POST /comments
- @description Create a new comment
- @body {content, postId}
- @access Login required

- @route PUT /comment:id
- @description Update a comment
- @body
- @access Login required

- @route DELETE comments/:id
- @description Delete a comment
- @body
- @access Login required

- @route DELETE /comments/:id
- @description Delete a comment
- @body
- @access Login required

### Reaction APIs

- @route
- @description
- @body
- @access Login required

- @route
- @description
- @body
- @access Login required
