# dialectica-app
Test assesment for a company

# Reqs
## Overview

The assignment consists of several tasks.
Some are required and others are marked as **[OPT]** to indicate they are optional (nice to have)s.
Where tasks are presented in a hierarchy layout, if a parent is **[OPT]** then children are also.

In general you should plan for **8-10 hours** of your time,
but you are free to spend more time if you wish.

You will have **1 week** to complete the assignment.

## Objective

To build a modern web app that functions as a minimal github repo explorer.

The repo identifier will be input by the user, e.g. "facebook/react" and,
_for the purpose of the assignment_,
you will have to present categories of data such as
Issues, Pull Requests, Forks, Languages, Likes
through a UI inspired by Dialectica's product designs.

**Check out [THIS LINK](https://res.cloudinary.com/sincospi/image/upload/v1589398706/dialectica/dialectica_design_elements.png)** for designs.

![](https://res.cloudinary.com/sincospi/image/upload/c_scale,w_960/v1589276941/dialectica/assignment_filtered_table_1.png)
_Mockup for guidance (ignore languages tab)_

## Preparation

You will use React and will be utilizing github's [graphql endpoint](https://developer.github.com/v4/).

This repo contains your starting point.

It is a [create-react-app](https://create-react-app.dev/docs/getting-started),
uses [yarn](https://alligator.io/nodejs/npm-yarn-cheatsheet/) package manager,
is configured with
[Prettier](https://prettier.io/docs/en/editors.html)
and
[Apollo Client 3](https://www.apollographql.com/docs/react/v3.0-beta/).

Note: You are NOT confined to use Apollo (you may remove it) and are encouraged to use any additional libraries you wish.

## Tasks

### Obtain a github access token

Simply follow Github's instructions
for [creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)

Note, you may wish to use a tool like
[GraphiQL](https://www.electronjs.org/apps/graphiql)
for building your queries initially.

### Page layout

The page should have 2 input fields.
One for visitor's `Access Token` and the other for the desired repo identifier e.g. `facebook/react`.
It is suggested that these values are also stored in localStorage for them to persist if the page is refreshed.

Repo name and description should follow.

### Tabs

Categories of data presented will be arranged in a tab layout.
Tabs should have counters that implement default filters
e.g. Issues should show **open** issue count (see below for defaults).

Each tab should have associated routing (see below).

### Tab content

A table with following properties:

#### Issues

- Router: `/issues`
- Columns [number, title, author, commentCount, createdAt, state]
- Filter by state: [Open, Closed, All], defaults to Open
- Sort by: [commentCount, createdAt], default commendCount desc

#### Pull Requests

- Router: `/pull-requests`
- Columns [title, author, commentCount, createdAt, state]
- **[OPT]** Filter by state: [Open, Closed, Merged], defaults to Open
- **[OPT]** Sort by: [commentCount, createdAt], default commentCount desc

#### Forks

- Router: `/forks`
- Columns: [repoAndOwnerName, description, starCount, createdAt]
- **[OPT]** Filter by Privacy: [Public, Private, All], defaults is Public
- **[OPT]** Sort by: [starCount, createdAt], default starCount desc

#### All Tab Tables

Tables should implement

- Pagination
  - Up to 20 results in the first request
  - **[OPT]** Load more button to bring next 20
- **[OPT]** Button to toggle sorting between asc/desc
- **[OPT]** Filter dropdown. A results count, should be shown above the table.
  - The top level (tab) counts should not be effected by these filters.

### Star/Un-star Toggle

Implement a button for start/un-star toggle functionality.

Clearly indicate the total repo star count and the state (stared or not) for the user.

### **[OPT]** Language Chart

![](https://res.cloudinary.com/sincospi/image/upload/c_scale,w_140/v1589396749/dialectica/Screenshot_2020-05-13_at_22.03.13.png)

Github provides language (i.e. Javascript, Ruby, etc.) stats
in the form of number of files in each language.
Hence, create a chart to depict the % occupied by each one of the top 3 languages.
Any additional languages should be bundled under label "other".

You may use some charting lib like [chartjs](https://www.chartjs.org/samples/latest/charts/pie.html).

## Working knowledge of topics
   Vue 3  : 0%
   GraphQL: 0%
   Apollo : 0%
   TS     : 15%

Went for Vue 3 as I did have some knowledge of Vue 2. Little did I know of how different they are, especially when trying the new Composition API (which is more similar to REACT syntax) rather than the more familiar Options API

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
