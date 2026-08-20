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

## After Setup:

* [ ] Confirm hot reload works when you edit a file in `src`.
* [ ] Add a `.env` file for environment variables and prefix public values with `VITE_`.
* [ ] Initialize git and create the first commit if the project is new.
* [ ] Decide on a folder structure for components, pages, hooks, and assets.
* [ ] Add a linter and formatter (`eslint` and `prettier`) before writing feature code.
