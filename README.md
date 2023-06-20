# Car Community - Blog Application

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app) in order to create a platform where the car owners can share there experiences the car of any brand. 

## Benefits of this app
1. Whenever a user encounter any problem with there car they can update on this platform and aware others to rectify the problem
2. Users can gain knowledge

## Featues offered by the app
1. User Friendly
2. Share the post
3. Update/Edit the post (only authorised user of that post only)
4. Can see the lastest post on the top
5. Password is hashed

## Languages used for creating the project
1. `React (HTML, CSS, JavaScript)`
2.  `Express`
3.  `MongoDB`
4.  `NodeJS`

## Dependencies used along with their versions
1. `date-fns : ^2.30.0` : For formating the date
2. `multer: ^1.4.5-lts.1` : Middleware for handling multipart/form-data, which is primarily used for uploading files
3. `react: ^18.2.0` : Package contains only the functionality necessary to define React components
4. `react-dom: ^18.2.0` : Provides client-specific methods used for initializing an app on the client
5. `react-quill: ^2.0.0` : Rich-text editor as a React component
6. `react-router-dom: ^6.12.1` : Package contains bindings for using React Router in web applications
7.  `bcrypt: ^5.1.0` : A library to help you hash passwords
8.  `body-parser: ^1.20.2` : Parses data from the page
9.  `cookie-parser: ^1.4.6` : Parser cookies 
10. `cors: ^2.8.5` : Connect / Express middleware that can be used to enable CORS
11. `express: ^4.18.2` : To create a server (ex: 4000)
12. `jsonwebtoken: ^9.0.0` : Creating/authenticate keys 
13. `mongoose: ^7.2.3` : creating the database


## Middlewares used
```js
app.use(cors({ credentials: true, origin: "http://localhost:3000" }));
app.use(express.json());
app.use(cookieParser());
app.use("/uploads", express.static(__dirname + "/uploads"));
```


## Hashing the password
```js
const userDoc = await User.create({
      name,
      username,
      password: bcrypt.hashSync(req.body.password, 10),
    })
```

## JWT Token assignment

```js 
    jwt.sign(payload, "secret", (err, token) => {
      if (err) {
        return res.status(400).json(err);
      } else {
        return res.cookie("token", token).json({
          id: userDoc._id,
          name: userDoc.name,
          username: userDoc.username,
        });
      }
    })
```

##  Cookies authentication
```JS

  const token = req.cookies.token;
  if (token)
    jwt.verify(token, "secret", (err, info) => {
      if (err) throw err;
      res.json(info);
    });
```
    

    
## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
