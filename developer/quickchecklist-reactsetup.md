## Windows OS:

### Install Node.js:
* [ ] Go to the Node.js website (https://nodejs.org/) and download the LTS version for Windows.
* [ ] Run the downloaded installer and follow the installation instructions.
* [ ] Open a new command prompt and verify the install:
~~~
node --version
npm --version
~~~
### Open a command prompt:
* [ ] Press Win + R, type "cmd", and press Enter to open the command prompt.
### Create a new React project with Vite:
* [ ] Navigate to the desired directory where you want to create your project using the `cd` command.
* [ ] Run the following command to create a new React project:
~~~
npm create vite@latest my-react-app -- --template react
~~~
* [ ] If you want TypeScript, use this command instead:
~~~
npm create vite@latest my-react-app -- --template react-ts
~~~
### Navigate to the project directory:
* [ ] Use the `cd` command to navigate to the project directory:
~~~
cd my-react-app
~~~
### Install dependencies:
* [ ] Run the following command:
~~~
npm install
~~~
### Start the development server:
* [ ] Run the following command to start the development server:
~~~
npm run dev
~~~
* [ ] Open the local URL shown in the terminal (usually `http://localhost:5173`) in your browser.

## macOS:

### Install Homebrew:
* [ ] Open a terminal.
* [ ] Run the following command to install Homebrew:
~~~
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
~~~
### Install Node.js:
* [ ] In the terminal, run the following command to install Node.js using Homebrew:
~~~
brew install node
~~~
* [ ] Verify the install:
~~~
node --version
npm --version
~~~
### Create a new React project with Vite:
* [ ] Navigate to the desired directory where you want to create your project using the `cd` command.
* [ ] Run the following command to create a new React project:
~~~
npm create vite@latest my-react-app -- --template react
~~~
* [ ] If you want TypeScript, use this command instead:
~~~
npm create vite@latest my-react-app -- --template react-ts
~~~
### Navigate to the project directory:
* [ ] Use the `cd` command to navigate to the project directory:
~~~
cd my-react-app
~~~
### Install dependencies:
* [ ] Run the following command:
~~~
npm install
~~~
### Start the development server:
* [ ] Run the following command to start the development server:
~~~
npm run dev
~~~
* [ ] Open the local URL shown in the terminal (usually `http://localhost:5173`) in your browser.

## Ubuntu/Linux:

### Install Node.js:
* [ ] Open a terminal.
* [ ] Run the following commands to install the current Node.js LTS using NodeSource:
~~~
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
~~~
* [ ] Verify the install:
~~~
node --version
npm --version
~~~
### Create a new React project with Vite:
* [ ] Navigate to the desired directory where you want to create your project using the `cd` command.
* [ ] Run the following command to create a new React project:
~~~
npm create vite@latest my-react-app -- --template react
~~~
* [ ] If you want TypeScript, use this command instead:
~~~
npm create vite@latest my-react-app -- --template react-ts
~~~
### Navigate to the project directory:
* [ ] Use the `cd` command to navigate to the project directory:
~~~
cd my-react-app
~~~
### Install dependencies:
* [ ] Run the following command:
~~~
npm install
~~~
### Start the development server:
* [ ] Run the following command to start the development server:
~~~
npm run dev
~~~
* [ ] Open the local URL shown in the terminal (usually `http://localhost:5173`) in your browser.

## After Setup (the parts that bite you in week two):

* [ ] Confirm hot reload works when you edit a file in `src`.
* [ ] Add `.env` / `.env.example`; only `VITE_` keys are exposed to the browser — never put a private API secret there.
* [ ] `import.meta.env.PROD` vs `DEV`: API base URL is not hardcoded to localhost in the production build.
* [ ] Initialize git; `.gitignore` includes `dist`, `.env`, and editor folders.
* [ ] Path alias (`@/`) in both Vite and `jsconfig`/`tsconfig` so IDE and build agree.
* [ ] ESLint + Prettier + `eslint-config-prettier` so the two do not fight; run on CI, not only save.
* [ ] React Router (or your router) `BrowserRouter` basename if the app is not at `/`.
* [ ] `index.html` title and favicon are not the Vite defaults before the first client demo.
* [ ] Strict Mode double-invokes effects in dev — do not “fix” that by removing Strict Mode to hide a subscription bug.
* [ ] Decide query/data library (React Query, etc.) before you invent five `useEffect` fetchers.
* [ ] `npm run build` and preview the **production** bundle once; some bugs exist only in prod minify.
