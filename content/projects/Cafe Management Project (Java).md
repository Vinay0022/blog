+++
title = "Cafe Management Project"
+++

### Things must know
- Netbeans
   - For undecorating the window select the undecorated in the Frame properites it will disable the minimize , exit and maximize option in the window after running.
   - For generating the window at the center of the screen tick the Generate Center option in the code tabe of the frame.
- What is JFrame?
    - It's like a page.
    - JFrame is a class type container which inherits the java.awt.Frame class.
    - It acts likes a main window which holds the components like buttons, fields, texts etc and a GUI is created.
- What is JPanel?
    - It's like a canvas board on the wooden frame.
    - JPanel Will holds the componets together.
    - *You need absolute layout so components can be placed on top of each other.*
    - Colors are only applicable to JPanel not for JFrame.
- Difference between JPanel And JFrame?
    - JPanel is added on top of JFrame and JPanel extend the JFrame.
    - JPanel is a container whose parent is java.swing.JComponent.(JSwing)
    - JFrame is a container whose parent is java.awt.Frame.(Abstract Window Toolkit(awt)).
    - Colors are only applicable to JPanel not for JFrame.
- How to set the password visible and invisible in JPasswordField
    - Use setEchoChar((char)0) method in JPasswordField to show the characters while typing
    - Use setEchoChar('*') method in JPasswordField to make all the characters look * while typing.
- How to make the Username input box to detect if the user have inputed number and give them warning.
    - Make a basic if condition that if the inputed character is not between 0 and 9 then it will return true right so you surround that with not making it like if the character are alphabate then it will always return true and the not condition will return false then if will not run if it's vice-e-versa then shows a jOptionPane.showMessageDialog and give warning.
- How to add dragging functionality for window
    - make a 2 global variables xx and yy which will hold the co-ordinates of the mouse relative to the jPanel when clicked.
    - We need to events MouseClicked and MouseDragged.
    - MouseClicked it will store the values of mousepointer relative to the jPanel via getX() and getY() methods of evt i.e. event object.
    - MouseDragged event will store the value of XOnScreen and YOnScreen co-ordinates value relative to the screen and store in x and y variables.
    - Then we will set the location of the window inside the MouseDragged event based on the difference between the current sceen co-ordinates i.e. x and y and the inital xx and yy.
- A glowing effect for sign up
    - It's not that important but you can try it for fun.
    - You can use for loop with double as initiliazor and inside it you need a String variable which will hold the value of 'i' and then parse it into float and store it in variable and use this for opacity setOpacity(float);
- What is PreparedStatment and why we use it?
    - PreparedStatment allows you to set parameters in the SQL query, which helps to prevent SQL injection. Paremeters can be set using setter methods such as setInt, setString, setDouble,... etc.
    - To create an instance of PreparedStatment we use preparedStatement() method of Connection interface.
- JFileChooser
- All Frames and models
    - Reji and AdminReji holds the sql instructions and methods of it.
    - Product and Admin holds the structure of the data and setters and getters of that data.
- What will happen if you remove the jTable1.setModel from ManageProductFrame
    - The line is responsible for setting a new model for the jTable1
    - If we comment it out then the JTable1 will not be updated it will remain the same and after this line getallProducts function is called which will retrive the updated data from the database and new row will be added in the JTable1 because the previous one was not removed.
    -  jTable1.setModel(new DefaultTableModel(null, new Object[]{"ID","Name","Price","Image"}));
    - In the above code we set the New DefaultTableModel of jTable1 it takes 2 parameters one is data and other is columnNames. data is set to null and columnNames is set to what was it before.
      *ResultSet in Java.SQL starts the index from 1.*

- LocalDate and DateTimeFormatter
    - Use the LocalDate to get the current date and formate it using the DateTimeFormatter and set it's lable.


- Tech Stack
   - Frontend
   - JSwing
   - JFrame
   - Database
   - MySQL
## Structure of Database and Frames , models

#### Admin Table
- id
- username
- password
-  s_ques
-  ans

### Cart Table
- cart id
- product id
- product name
- qty
- price
- total

### Product Table
- id
- name
- price
- image

### Payment Table
- payment id(pid)
- customer Name(cName)
- products id(proid)
- product Name(pName)
- totalPrice(total)
- pdate



### Steps
* First Create all the Fronted using JFrame and JPanel i.e JSwing and AWT.
    - HomeFrame
    - ViewOrdersFrame
    - SignUpFrame
    - StatisticsFrame
    - OrderFrame
    - ManageProductFrame
    - CartFrame
    - AllProductsFrame
    - ForgotPasswordFrame
    - SignUpFrame
    - LoginFrame

* Second Create all logic for the Frames(java files for it) Netbeans will create automatically for it.
    - Home
    - ViewOrders
    - SignUp
    - Statistics
    - Order
    - ManageProduct
    - Cart
    - AllProducts
    - ForgotPassword
    - SignUp
    - Login

* Create database cafe
    1. admin
	    - Sign Up data is stored in the admin table.
    2. cart
	    -  It contains the data of the tableContents from CartFrame.
    3. product
	    - It contains the data from the ManageProductFrame's tableContents.
    4. payment
	    - It contains the data from the ViewOrdersFrame's tableContents;

* Models
    - Dao(Data Access Object) holds all the method  that run the quries for all the frames excluding Admin and AdminDao holds the sql instructions for Admin and methods of it.
    - Admin, Product, Payment, Cart, Calculate holds the structure of the data and setters and getters of that data.
    - MyConnection  contains the logic related to establish the connection to the mariadb database.

* Working of Frames
 1. Login
 - Successful Login
    - First we need to create and Object of AdminDao model because we need to use the queries of AdminDao to check if the username , password is correct or username exist or not.
    - When you fill up all the login Field username, password and pressed login it will get the string from the inputField(username,password) and put it inside a variable and will run the SQL query of the model AdminDao through the Object we have created.
    - It will get the maxId from the admin table  and return maxId+1 to make sure there is at least one admin.
    - Now it check if the admin exist or not AdminDao SQL query and etc.

 - Unsuccessful Login
   - If the username is incorrect it will promte and error message.


 - User does not exit
   - It will promte a warning window and show message to sign up.
   - After clicking Sign Btn it will close the Login page by making it's visiblity false and show Sign Up Frame.
   - Sign Up also needs to have Object of AdminDao because it contains the SQL Qeuries for inserting the Admin to the database which will be triggered after clicking the saveBtn and also it will run the query to get the maxId and return max+Id so it will be the Id for new User.
   - It will check if user name exist or not from the AdminDao SQL Query. If it doesn't then it will create an Object of Admin to set up the admin variables via setters.then this admin object is passed to the insert method of AdminDao which will run SQL query and get the parameters for it via the getters of admin.


2. Order
  -
