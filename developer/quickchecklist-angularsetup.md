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

## After Setup (the parts that bite you in week two):

* [ ] Confirm the app reloads when you change a component file.
* [ ] Generate features with `ng generate`; do not hand-create files that miss `standalone`/module wiring.
* [ ] `fileReplacements` / application environments: production API URL is not still `localhost`.
* [ ] Lint on CI. Recent Angular does not always ship `ng lint` until you add the ESLint schematic — add it or use another linter, but run it in CI.
* [ ] Strict templates (`strictTemplates`) on if the team uses TypeScript strictly.
* [ ] Interceptors: auth token, 401 redirect, and correlation id — decided before the fifth service copies `HttpClient` headers.
* [ ] `providedIn: 'root'` vs component providers so you do not get two copies of a stateful service.
* [ ] `ng build` (production configuration) locally; budget warnings for bundle size are treated as real.
* [ ] `index.html` title/favicon not left as the CLI default for client demos.
* [ ] Initialize git; ignore `/dist`, `/tmp`, `.angular`.
