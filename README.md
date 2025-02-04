# Create a MERN Stack App:

## How to create a frontend part for the MERN App:
### Step-1

Open the main root folder and create a "frontend or client" folder manually. open the folder using the terminal or git_bush. </b>

Copy and paste the command to create the @Vite latest app with yarn.
```bash
yarn create vite
```

### Step-2

Provide the **Project name: »** `my-project` or `./`

### Step-3

**Select a framework: »** - Use arrow-keys. Return to submit. (select only one option)

<li>vue</li>
<li>React</li>
<li>Others</li> ,etc.

### Step-4

**Select a variant: »** - Use arrow-keys. Return to submit. (select only one option).

<li>TypeScript</li>
<li>TypeScript + SWC</li>
<li>JavaScript</li>
<li>JavaScript + SWC</li>

### Step-5

Provide the command `cd **project-name**`.

### Step-6

Provide the command `yarn` for the installation or creation of the **node_modules** folder.

### Step-7

Finally, Copy and Paste the command to run the project.
```bash
yarn run dev
```

## How to create a backend part for the MERN App:

### Step-1

Open the main root folder and create a "backend" folder manually. open the folder using the terminal or git_bush. </b>

Copy and paste the command 
```bash
yarn init
```

### Step-2

Provide the **question name (backend): »** `my-project-server` 

### Step-3
- Click the Enter button for **question version (1.0.0):**
- Write some description of the project in **question description:**
- Click the Enter button for **question repository url:**
- Provide the author's name in the **question author: »** `@nurulazamDev`
- Double click the Enter button for **question license (MIT):** and **question private:**.

Then, successfully created or Saved the package.json file in the backend folder.

### Step-4

Copy and paste the command to install the packages.
```bash
yarn add express mongodb mongoose cors jsonwebtoken cookie-parser dotenv bcryptjs nodemon
```

### Step-5

Provide the lines in the backend => package.json file under the `"main": "server.js",` line.

```bash
 "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js",
    "start-dev": "nodemon server.js"
  },
```

### Step-6

Finally, Provide the command to run the backend project.
```bash
yarn start-dev
```
