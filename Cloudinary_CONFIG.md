## cloudinary.js

#### paste this code in cloudinary.js and change your cloudinary configuration

```javascript
import { v2 as cloudinary } from "cloudinary";


const connectCloudinary = () => {
  cloudinary.config({
    cloud_name: process.env.CLOUDINARY_CLOUD_NAME,
    api_key: process.env.CLOUDINARY_API_KEY,
    api_secret: process.env.CLOUDINARY_API_SECRET,
  });

};

export default connectCloudinary;
```

### usage

in <b>server.js or index.js</b>

import this file in your main file

```javascript
connectCloudinary();
```

In your image uploading file

use this to upload images

```javascript
const imageUrl = req.files.map(async (file) => {
      const response = await cloudinary.uploader.upload(file.path);
      return response.secure_url;
    });
```

After that store this url in any database