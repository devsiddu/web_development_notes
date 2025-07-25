## multer.js

multer configuration for express js backend

```
import multer from 'multer'

const upload = multer({
    storage: multer.diskStorage({})
})

export default upload;
```

## Usage 
In your router user upload function 

Eg-
```
const app = express();

app.post("/add-image", upload.array("images", 4), (req,res)=>{
    //your function
});
```
