+++
title = "NextJs"
date = 2019-11-28
+++

NextJs is a framework of react js which provides additonal features like routing and solves other problmes like bundling and tooling for the application.
NextJs is an declerative way to make application.

### Prerequisite for the NextJs is follows:

---

- what is Synchrous and Asynchronous.
- Async/await function.
- Arrow Functions.
- Basics of React (Components,Props,State).
- Mapping or methods of iterating throug array.
- How the browser works.
  (Whenever user visits a site it requests a page which is html the server respond this request and send the html page the browser converts this html page into the DOM(it s a representation of the html into a hiearchial tree).The DOM acts as a bridge between the user interface and the your code).
- 'Thinking in React' part of the offical documentation of React is pretty good to go through.

### New Things

---

- Bundling. -- resolves file dependecies and merge packages.
- code splitting. -- splits the applications bundle into smaller chunks for each routes /post/pre-redering so it will split the code for 'post'and 'pre-rendering'so only that particular part is getting renderd when we go to that URL.
- minifying. -- In our code we have lots of unecesarry code e.g. comments, indents, spaces.So minifying remove those and reduces the file size to improve the performance.
- compiling. -- Whenever we go from build to production enviroment compiling happens in NExt.js.It converts the code from one language to another language.

### API Routes

---

- to creat a API Routes create a directory in '/pages/api/hello.js', 'hello.js' contains the API endpoint.

### Rendering
1. Client-Side Rendering
2. Pre-rendering
   - Server-sider rendering -- HTML is generated on each requests.
   - Static Generation -- happens at build time generates HTML. The pre-generated HTML is reused for every requests.

| Sever-Sider Rendering                               | Static Generation                                                     |
| --------------------------------------------------- | --------------------------------------------------------------------- |
| Slow                                                | Fast                                                                  |
| on every request the HTML is generated              | happens at build time and HTML generated is reused for every requests |
| Should be used when the data is changing constantly | otherwise use this.                                                   |

## **directory name must be in lowercase**

- **top level directory**
- pages directory -- It is in top level directory for individual pages route for each page will be like /post/ssr- if we have ssr- inside a post directory.
- components directory -- global components
- styles directory --It is a top level directory . It contains files for global css and normal css.
- lib directory -- It is a top level directory .It contains files for fetching data
- \_app.js -- It is in pages/api/ .It is a special type of file which we can use to import global styles.
- component level sytles can be achieve by using CSS moudules i.e. util.moudles.css in the components directory.

## ** lib/posts.js **

-lib directory i have created an posts.js which does the fetching of the data from the file system.We can also fetch the data from the external API and data fetching fromm the database

- I will explain what have i done in the posts.js.
- I have imported 'fs', 'path', 'gray-matter' , 'remark' function from remark and 'html' from 'remark-html'.
- fs -- deals with the file systems like writing and reading of the files.
- path -- helps with the getting the path of the directory.
- gray-matter -- Is used for parasing the metadata of the markdown files.
- html form 'remark-html' -- convert the markdown file into HTML string.

- const postsDirectory = path.join(process.cwd()."posts");
  In the above code i have got the path of the posts directory by using the path module `porcess.cwd(),'posts` get the current working directory ."posts" means look for the posts directory and we will have path /nextjs-blog/posts/
- `export function getSortedPostsData()`
  this function is for reading the contents of the file and returning it.
- `const fileNames=fs.readdirSync(postsDirectory)` -- it will read synchornously the contents of the directory i.e all the files and return the array of the file names or directory.

