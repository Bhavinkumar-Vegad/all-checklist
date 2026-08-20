## Install Node.js:

* [ ] Install the current Node.js LTS from https://nodejs.org/ or your package manager.
* [ ] Verify the install:
~~~
node --version
npm --version
~~~

## Create the Project:

* [ ] Open a terminal in the folder where you want the app.
* [ ] Create a new Next.js app:
~~~
npx create-next-app@latest my-next-app
~~~
* [ ] Choose TypeScript, ESLint, App Router, and a src directory if that matches your team.
* [ ] Move into the project:
~~~
cd my-next-app
~~~

## Run Locally:

* [ ] Start the dev server:
~~~
npm run dev
~~~
* [ ] Open `http://localhost:3000` and confirm the starter page loads.
* [ ] Confirm Fast Refresh works after you edit a page or component.

## Project Basics:

* [ ] Set up `.env.local` for secrets and never commit it.
* [ ] Prefix public values with `NEXT_PUBLIC_` only when the browser must read them.
* [ ] Decide where server actions, route handlers, and client components will live.
* [ ] Add a root layout, metadata, and a favicon.
* [ ] Configure `next.config` for images, redirects, and any required headers.

## Quality:

* [ ] Run `npm run lint` and fix issues before the first feature.
* [ ] Add a formatter and agree on import order.
* [ ] Initialize git and create the first commit.
* [ ] Add a README with setup, env vars, and useful scripts.
