# Ferrivore

A website for idea discovery. Hosted at https://ferrivore.gerardkeiser.com.

## Motivation

Ferrivore helps you find ideas that are interesting. Other services promise this, but their recommendation algorithms tend to show you things that you already agree with, from people you already follow. Ferrivore, on the other hand, has no user likes or follows; liking a post by a user does not automatically prioritize that user's other posts. It also encourages you to like ideas regardless of how much you agree with them, so that the algorithm can recommend all interesting ideas and not just sort you into a filter bubble.

## Features and Usage

Upon login, users view two main pages: the homepage and a page with previously rated ideas.

On the homepage, users can view one idea at a time, and can either rate their agreement with the idea on a 0-7 scale, or dismiss the idea as uninteresting. Thereupon they can see how other users rated the idea, and request another idea. Users can select whether they want the next idea to be one they will probably agree or disagree with.

The first idea on the homepage will always be one predicted to cause disagreement.

On the ideas page, users can see a list of all ideas they have previously rated, and can also switch to ideas they have posted themselves. From there they can view additional details for a post, and also change their ratings or, if they have posted it, delete the post.

They can also edit their username, email, and password, as well as post their own ideas.

There is no simple way to check another user's posts. This is deliberate.

## Implementation

The backend is a RESTful API written with the Flask framework and connected a Neo4j database.

The frontend is a React app using React Router and written with TypeScript. It authenticates with the backend using JWTs.

## Install/Deploy

1. Start a Neo4j database. The default login details for testing and are in `__init__.py` in the backend, and the necessary constraints and indices can be found in `set_db_properties` in the `seed.py` file.
2. If deploying, make a `.env` file and edit the `Dockerfile` for the backend. This should be unnecessary if running locally with `flask run`.
3. The frontend connects by default to `https://ferrivore.gerardkeiser.com/api`; set the `REACT_APP_BASE_URL` to change this.

## Upcoming Features

- [ ] Many improvements to the collaborative filtering system

- [ ] System to commend posts for being particularly rational or well-written, which boosts them in the recommendation system

- [ ] Reporting system to remove abusive posts

- [ ] Password recovery system

- [ ] Better styling, as always
