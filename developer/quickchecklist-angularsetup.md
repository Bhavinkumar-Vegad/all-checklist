## Windows:

### Install Node.js and npm:
* [ ] Download the Windows installer from the official Node.js website (LTS version).
* [ ] Run the installer and follow the instructions to complete the installation.
* [ ] Verify the installation by opening a new command prompt and running the following commands:
~~~
node --version
npm --version
~~~

### Install Angular CLI:
* [ ] Open a command prompt and run the following command:
~~~
npm install -g @angular/cli
~~~
* [ ] Verify the installation by running the following command:
~~~
ng version
~~~

### Create a new Angular project:
* [ ] Open a command prompt in the desired directory for your project.
* [ ] Run the following command to create a new Angular project:
~~~
ng new my-angular-project
~~~
* [ ] Answer the prompts for project settings (such as routing, stylesheet format, and SSR).

### Navigate to the project directory:
~~~
cd my-angular-project
~~~

### Serve the Angular application:
~~~
ng serve
~~~
* [ ] Open a web browser and visit `http://localhost:4200` to see your application running.

## macOS:

### Install Homebrew (Package Manager):
* [ ] Open a terminal and run the following command:
~~~
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
~~~

### Install Node.js and npm:
* [ ] Run the following command in the terminal:
~~~
brew install node
~~~
* [ ] Verify the installation by running the following commands:
~~~
node --version
npm --version
~~~

### Install Angular CLI:
* [ ] Run the following command in the terminal:
~~~
npm install -g @angular/cli
~~~
* [ ] Verify the installation by running the following command:
~~~
ng version
~~~

### Create a new Angular project:
* [ ] Open a terminal and navigate to the desired directory for your project.
* [ ] Run the following command to create a new Angular project:
~~~
ng new my-angular-project
~~~
* [ ] Answer the prompts for project settings (such as routing, stylesheet format, and SSR).

### Navigate to the project directory:
~~~
cd my-angular-project
~~~

### Serve the Angular application:
~~~
ng serve
~~~
* [ ] Open a web browser and visit `http://localhost:4200` to see your application running.

## Ubuntu/Linux:

### Install Node.js and npm:
* [ ] Open a terminal and run the following commands:
~~~
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
~~~
* [ ] Verify the installation by running the following commands:
~~~
node --version
npm --version
~~~

### Install Angular CLI:
* [ ] Run the following command in the terminal:
~~~
npm install -g @angular/cli
~~~
* [ ] Verify the installation by running the following command:
~~~
ng version
~~~

### Create a new Angular project:
* [ ] Open a terminal and navigate to the desired directory for your project.
* [ ] Run the following command to create a new Angular project:
~~~
ng new my-angular-project
~~~
* [ ] Answer the prompts for project settings (such as routing, stylesheet format, and SSR).

### Navigate to the project directory:
~~~
cd my-angular-project
~~~

### Serve the Angular application:
~~~
ng serve
~~~
* [ ] Open a web browser and visit `http://localhost:4200` to see your application running.

## After Setup:

* [ ] Confirm the app reloads when you change a component file.
* [ ] Generate a feature module or standalone component with `ng generate` instead of creating files by hand.
* [ ] Configure environments (`environment.ts` / `environment.prod.ts` or `application.json` based on your Angular version).
* [ ] Enable linting with `ng lint` and agree on formatting rules with the team.
* [ ] Initialize git and create the first commit if the project is new.
