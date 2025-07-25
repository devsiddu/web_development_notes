## db.js

#### Paste this code in db.js and change your MongoDB connection configuration

```javascript
import mongoose from "mongoose";

export const connectDB = async () => {
  mongoose.connection.on("connected", () => console.log("DB is connected"));
  await mongoose.connect(`${process.env.MONGODB_URI}`); // replace with your MongoDB URI
};
```

## Usage

in your main file (e.g., server.js or index.js), import and call the connectDB function:

```javascript
import { connectDB } from "./db.js";

connectDB();
```
