+++
title = "React"
date = 2019-11-28
+++

### Concepts
- Component
    - It's a piece of reusable code which represents it own logic and appearance.UI is made up of many these components and sometimes entire page. It's is a javascript function that return a markup here JSX markup is used . JSX is combination of both javascript and html. The name of component must start with captial letter like MyButton and html with lowercase. It return only one element e.g div tag so in order to
      use multiple tags we need to wrap them inside

```javascript
<div>
</div>
```

or a wrapper
```javascript
<\>...\</\>
```

- Escaping the JSX We can escape the JSX and use javascript so we can embed our variable and display it by using {} curly braces. we can also use this inside a className attributes like *src={}*

### state
- which holds some information which we want to display. Suppose we have two same components and we are nesting it in a Main component then these two will have it's own state.

### conditional rendering
- It is important part We can render a list using some condition. For condition we can use if else statement or ternary operator condtion *?* but the ternary operator works inside the JSX while if else not.

- If else example

```javascript
let content;
if (isLoggedIn)
{ content = <AdminPanel />;
}
else
{ content = <LoginForm />{=html}; }
return (
<div>
    {content}
</div>
);
```

###  Rendering lists
- mapping is important concept one must learn it. map works like this
in below code the function can be an anonymous arrow function.
```javascript
array.map(function(parameters(first parameter is each
item)){//body of the function}
```

- arrow function version
```javascript
array.map((parameters)=>{//body of the function}
```


### Hooks
   - Hooks are inbuilt functions in React they start with use like useState
     1. useState
       - useState  is used to keep the track of one date and to set it whenever we want it.
     2. useReducer
     - It is mostly when you have two or more states and your changing that states at the same time in same element(e.g button)
     3. useEffect
     - It is mostly used for API calls. Note you should pass empty array at the end  so the api will get called once if you don't want any specific state to call it.If you want any specific state to call it after it changes then you should pass the name of the state inside the array.
     4. useRef
      - If you think you can solve a particular task with vanilla js then you should use useRef. or it is very useful when you want to manipulate dom and access DOM. e.g. is focusing on input or clearning an input after clicking the add button in todo-list.
     5. useLayoutEffect
     - It triggers even at the same time of first rendering.It is called before the useEffect. so it's useful when you want to display something before the data is getting displayed like UI stuff. but if you still decided to use useEffect then you can see the data which was before appeared and disappeared in a milliseconds. because it gets rendered after the first render.
     - But most of the times it's better to avoid to use useLayoutEffect because of the performance issue.
   6. useImperativeHandle
      - It can be used to change/use the state which is inside a child state or the child state can be in separate file also and changing is done via the parent component.Note it requires to make the child component as forwardref.
   7. useContext
      - It is used when we have one or more state and instead of passing the props(in our case states) to each child . we can just wrap it in a AppContext.Provider and access the values in child component.It makes more sense to use it .if the child component have lots of props. Note Child Component need useContext in it and we can create context using creatContext in parent component.

### Routing(with react-router-dom)
   - 3 things we need to import first BrowserRouter , Routes, Route
   - BrowserRouter or Router provides where we can use the react-router-dom. like if we put Link outside the BrowserRouter it cannot work because Link is part of reac-router-dom. It needs to be inside the BrowserRouter so we can use it.
   - Routes includes list of Route we want to have.
   - Route just provides the path.
   - For navigation through website there is *Link* Component. as the name says it provides link like 'a' tag in html;

 ### React Js and Node Js
   - To create react with frontend and Backend(API + Server) with node. We need to have two folders one for backend and other one is our react frontend project folder.
   - In frontend we require axios which is used for data fetching.
   - In backend(backend folder) we need to install express, cors,mysql,bcrypt,body-parse, express-session , cookie-parser . All of this dependency is also called middlewares. Middlewares is a software or functions that have access to the request and response objects and can perform various tasks such as modifying the request or response, terminating the request-response cycle, or passing control to the next middleware in the stack.
   - Middlewares as the name says it runs between request send by client(browser) and response sent by the server.
   - ( ) Let's see what's the purpose of each of this dependency
     1. express is used for handling the HTTP requests, routing
     2. cors(cross-origin resource sharing) is a protocol  which is used so we can be allowed  to use script which is running on client to interact with the resources from different domain i.e allow to send data from client to server.
     3. mysql is used for setting up the connection with MySQL database.
     4. bcrypt is used for hasing passwords we used with salts so we can add layer of security to it. it is nothing but adding some random text at the end of password.
     For Cookies and Session
     5. we need to add origin,methods(like GET,POST) , credentials in app.use(cors({...})) for using cookies.
     6. body-parser we need body-parse to parse the data comming from client (i.e. urlencoded data it's a data that is in the url that is data of form when we submit form with method POST and it's in the form of urlencoded data it follows the format like key-value paris, space is represented as %, key and values are separated with = and different key-value pairs are separated using &). it parsed the urlencoded data(it converts the data typically into an object in the request body) and the parsed data can be accessed  in the router handler through req.body i.e. request body.
     7. express-session to create a session so we can save it and use it to check if user is already loggedin or not it contains methods like  key: "userId",
	    secret: "socks",
	    resave: false,
	    saveUninitialized: false,
	    cookie: {
	        expires: 60 * 60 * 24,
	    }.

