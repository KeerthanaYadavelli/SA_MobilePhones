# SA_MobilePhones
Sentiment Analysis for Mobile Phones
Our goal is to help you find the best mobile phone, that will suit your needs. Customers can view various mobile phone reviews provided by the users of our website. Our website provides genuine rating based on the user comments. We use advanced technology to calculate the ratings of the latest cellphones. As the ratings are calculated by the machine learning algorithms there will be no bias. We use the Naive Bayes algorithm to calculate the ratings from the user reviews. Customers can register in our website to purchase and review the phones. Once registered, users can view the various phone collections. Customers can trust our user reviews and buy their favorite phones from our website.

Initial Setup: Please upload the entire folder “Front-end” to the server. All the files are arranged in their respective folders.
Please import Database related files from the folder Database Tables.
Live link of our web application: 
https://in-info-web4.informatics.iupui.edu/~smadishe/Project_Test_version2/loginSA.php
Database connectivity: 
config/database.php – Contains class definition related to database connectivity – Server related information
Database Tables: User, Product, product_image, Review
CSS: libs/css/custom.css – CSS styling tags are defined here
Bootstrap: accessed through MaxCDN through below link
https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css
Class definitions:
* -	Objects/product.php – Product
* -	Objects/product_image.php – ProductImage
* -	Objects/review.php - Review
Images:
Uploads/images – Contains jpg files of all images of the available products.
loginSA.php – Login Page
* -	Home – Linked to loginSA.php
* -	AboutUs – Linked to AboutUs.php
* -	Register – Linked to registerSA.php
If Login details are entered:
      -	Successful Login – afterLoginSA.php
      -    Unsuccessful Login – Error – User not registered or Password is incorrect
AboutUs.php – Motivation behind our website
* -	Home – Linked to loginSA.php
* -	Register – Linked to registerSA.php
* -	Login – Linked to loginSA.php
* -	Logout – Linked to logoutSA.php
RegisterSA.php – registration page for the users
* -	Home – Linked to loginSA.php
* -	Login – Linked to loginSA.php
* -	Logout – Linked to logoutSA.php
Successful signup – Data is inserted into User table
-        Redirected to loginSA.php
Unsuccessful signup – Error – Problem occurred in signing up, please try again
-        Redirected to registerSA.php
afterLoginSA.php – Displays successful login of the user and allows to navigate to different pages
* -	Home – loginSA.php
* -	Products – products.php
* -	Logout – logout.php
navigation.php - To design navigation bar
* -	PhoneMax - products.php
* -	Products - products.php
* -	Cart - cart.php
* -	Logout - logoutSA.php
layout_header.php - To design the header layout
	Includes - navigation.php
	Linked to -  Max CDN bootstrap framework 
* -	custom.css
 
Layout_footer.php - To design the footer part of the web page
* -	Includes javascript functions
    * -	For adding product to the cart  - linked to add_cart_to.php
    * -	For updating quantity of a product in the cart - linked to update_quatity.php

Paging.php - to implement pagination techniques

Read_products_template.php - to define the template to display individual products on products display page i.e products.php
	Image of the product - linked to product.php
	Add to cart button - linked to add_to_cart.php
Includes - paging.php

Products.php -  Main page to display all the products
	Includes
    * -	config/database.php
    * -	objects/product.php
    * -	objects/product_images.php
    * -	layout_header.php
    * -	read_products_template.php
    * -	layout_footer.php

Product.php - to display information about a particular product
	Includes
    * -	config/database.php
    * -	objects/product.php
    * -	objects/product_image.php
    * -	objects/review.php
    * -	layout_header.php
    * -	layout_footer.php

Click Here to Enter Review button - Opens a modal 
				- Submit button of the modal - Linked to insert_review.php
Add to Cart button - Linked to add_to_cart.php
Update cart button (displayed if the product is already present in the cart) - Linked to cart.php

add_to_cart.php - to add a product to the cart
    * -	Linked to products.php

cart.php - to display cart
	Includes
    * -	config/database.php
    * -	objects/product.php
    * -	objects/product_image.php
    * -	layout_header.php
    * -	layout_footer.php

Update Button - Linked to update_quantity.php (through layout_footer)
Delete Button - remove_from_cart.php
Proceed to Checkout Button - checkout.php

update_quantity.php - to update quantity of a product in the cart
	Redirected to cart.php

remove_from_cart.php - to delete a product from the cart	
	Redirected to cart.php

Insert_review.php - to insert a review into Review table and Overall_rating into Product table in the database
	Redirected to products.php

Checkout.php - to view the order i.e all the items that are added to the cat for final review and to place order
	Includes
    * -	config/database.php
    * -	objects/product.php
    * -	objects/product_image.php
    * -	Layout_header.php
    * -	Layout_footer.php

Place Order Button - Linked to place_order.php

Place_order.php - To place the order
	Includes
    * -	layout_header.php
    * -	layout_footer.php

Logout.php - For logging out of the web application.
	Redirected to loginSA.php



Steps to prepare the input file for machine learning

    * 1.	Export Review table as CSV for MS Excel.


    * 2.	Select the first column entirely and click Text to columns in the Data tab of the excel sheet. Click ‘Delimited’ and click Next.


    * 3.	Check the Semicolon option and make sure the Text qualifier is quotes(“) and click Next.


    * 4.	In the Data Preview section select all the columns and click Text in Column data format section and click Finish.


    * 5.	The excel file is converted like below.


    * 6.	Headers are added to this file and this file will be the input for machine learning.



Steps to Access the ipynb(python) file for Machine Learning
(The Machine Learning folder contains all the files required)

    * 1.	Go to the site: https://colab.research.google.com/
	

    * 2.	Click Upload and load the file MultipleAlgorithms_MobilephoneRatingPrediction_1.ipynb

    * 3.	Click the folder icon marked in red


    * 4.	Click Upload highlighted in yellow


    * 5.	Upload the files Amazon_Unlocked_Mobile.csv, Review.csv and Sample_Submission.csv


    * 6.	Click on the first cell and the run icon highlighted, will appear. Click on the run icon to run that cell. Similarly run all the cells one by one in the same order to run the entire code.

    * 7.	After the below cell is run, Review_new.csv is generated. The other models beyond this cell are only for comparison and they take some time to run.


    * 8.	Now the Review_new.csv file can be seen on the left side when refreshed. Right click on the file to download it.


    * 9.	The predicted ratings from this file can be uploaded into the database by running the UpdateRating_fromcsv.php script.

    * 10.	 After all these steps, the ratings for the reviews can be seen on the specific product page where the review was submitted, when refreshed.

    * 11.	Click Upload and load the file MultipleAlgorithms_MobilephoneRatingPrediction_2.ipynb

    * 12.	 Repeat steps 3-6 (This file is only for comparing different machine learning models. This file takes several hours to run. We are not fetching any output from this file. We are only fetching output from the Naive Bayes model from the first file).
