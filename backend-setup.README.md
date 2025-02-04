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

### Step-7
create the `server.js` file manually.
Copy and paste the command in the server.js.
```bash
import cookieParser from "cookie-parser";
import cors from "cors";
import { config } from "dotenv";
import express, { json } from "express";
import { set, connect } from "mongoose";

import authRoutes from "./routes/auth.js";
import productRoutes from "./routes/product.js";
import userRoutes from "./routes/user.js";

config();

const app = express();
const port = process.env.PORT || 8000;

const corsOption = {
  origin: true,
};

// database connection
set("strictQuery", false);
const connectDB = async () => {
  try {
    // connect(process.env.LOCAL_DATABASE);
    connect(process.env.MONGODB_URL);
    console.log("MongoDB is connected");
  } catch (err) {
    console.log("MongoDB connection fail");
  }
};

// middlewares
app.use(cookieParser());
app.use(json());
app.use(cors(corsOption));

// Middleware for error handling in Express
app.use((err, req, res, next) => {
  if (err.name === "ValidationError") {
    const errors = Object.values(err.errors).map((error) => error.message);
    return res.status(400).json({ errors });
  }
  next(err);
});

// routes
app.use("/api/v1/auth", authRoutes);
app.use("/api/v1/users", userRoutes);
app.use("/api/v1/products", productRoutes);

app.get("/", (req, res) => {
  res.send("MNA .....'s Api is working");
});

app.listen(port, () => {
  connectDB();
  console.log("MNA .....'s Server is running on port" + " " + port);
});
```

### Step-8
create the `models`, `auth`, `Controllers`, and `routes` folders manually in the `backend` folder. More details are provided in the documentation project.

### Step-9

create the files in the `models` folders. 
- `models` =>  `UserSchema.js`, and `ProductSchema.js`...

create the files in the `auth` folders. 
- `auth` => `verifyToken.js`.

create the files in the `Controllers` folders. 
- `Controllers` => `authController.js`, `userController.js`, and `productController.js`...

### Step-9
##### models folders =>
- `UserSchema.js` code:
- `ProductSchema.js` code:

### Step-10
##### auth folder =>
- `verifyToken.js` code:
