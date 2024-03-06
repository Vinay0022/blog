+++
title = "Npm and Npx"
date = 2019-11-28
+++

* what is npm and npx?
   - npm is a node package manager which installs the packages from the it's registry you can see your devDependecies and production dependencies in package.json file where as npx is a tool which executes this installed packages.

- Difference between npm and npx.
   - npm(Node Package Manager) is a default package manager for Node.js which is used to installing,sharing and managing dependencies in Node.js Project. It allows you to install packages globally or locally, manage version and run scripts defined the package.json file.
   - with npm you can also publish your own packages to the npm registry.
   - npx(Node Packer Execute) is a tool that is bundled with npm. It is used to execute Node.js packages without installing them globally.


-  what is npx <package-name> init?
	- ( ) npx` is a tool that comes with npm (Node Package Manager) and stands for "Node Package Execute". It allows you to run Node.js packages without having to install them globally or locally.
	- When you run `npx <package-name> init`, you're typically initializing a new project using a package's initialization script. This command will execute the `init` script provided by the specified `<package-name>`. This script is often used to set up a new project, create necessary files or directories, and perform any initial configuration required by the package.
	- For example, if you have a package called `create-react-app`, you could run `npx create-react-app init` to initialize a new React application without needing to globally install the `create-react-app` package.
