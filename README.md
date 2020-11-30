### Hacknews frontend in React and backend in Elixir.
Site to list hackathons and form teams to participate.
`docker-compose up --build` to visit localhost:3000 to up the site.
- The commits show the evolution of code over time with TDD.
- Frontend is split into components, containers, actions, reducers.
- Vote.js is experimented with a different pattern of having component, container, actions, reducers in a single file.
- api calls happen in challengeApi.
- Backend controll flows from router, controller, repo, view.
- Data base is designed as follows.
    - Challenges has many to one relationship with Users as created.
    - Challenges has many to many relationship with Tags.
    - Challenge has one to many relationship with Teams.
    - Teams has many to many relationship with Users.
    - Challenges has many to many relationship with Users as voted.
- Authorization is provided using jwt.
- It is persisted in localStorage across relaunches.
- tailwindcss is used for styling.
- At later part, due to time constraints, repeated tests(tests of same type) were omitted.
- Sample tests for components, actions, reducers, views, controllers etc are added to show variations.

- `docker-compose up --build` to run. To run separately follow below instructions.

### To Run React:
- npm install
- npm test
- npm start
- it will be served on port 3000.

### To Run Elixir:
- change config/dev.exs to have appropriate user name and password for postgress.
- In config/dev.exs url: "postgres://username:password@localhost/hack_news_backend_dev",
- mix deps.get
- mix ecto.create
- mix ecto.migrate
- mix phx.server
- it will be served on port 4000.