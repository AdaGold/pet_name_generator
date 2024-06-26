Part 1 - Setup

Clone the Pet Name Generator Repo
Create your venv
Install your requirements.txt
Create two databases in psql called pet_name_gen_dev and pet_name_gen_test
Create your .env file and add pet_name_gen_dev and pet_name_gen_test as the SQLALCHEMY_DATABASE_URI and the SQLALCHEMY_TEST_DATABASE_URI respectively.
Run your flask db init, flask db migrate and flask db upgrade
If you want, check your database to make sure it has the pet relation

Part 2 - Install OpenAI

Install the OpenAI python library using pip
Run the command pip freeze > requirements.txt to add OpenAI to the requirements file
Add your OpenAI (or Llama) Secret key to your .env file
Import OpenAI into your pet_routes.py file
Create an OpenAI client in your pet_routes.py file
If you are using llama, route the OpenAI client to the llama api using these instructions.

Part 3 - Write Your Pet Name POST Route
	
Now that everything is set up and OpenAI has been installed, write a helper function that will take the correct parameters to generate a suggestion for a pet’s name given its species, color and personality. Work with your group to write a prompt to feed into either OpenAI or Llama that will generate a name for your pet with the parameters given. Feel free to test out a few prompts and make sure to use print statements to analyze the response you get from each. 
Once you’ve got a working prompt and feel satisfied with your understanding of the response, write the add_pet function to add a pet to the database. Your request body should only include the pet’s species (type), personality and color. The name should be generated using AI and then added to the Pet object which then gets sent to the database. Remember that you may have to tweak the string you receive in order to effectively add it to the Pet object.  When you are finished, write a GET method that will return a list of the Pet objects. 

Part 4 - (Optional) Write a PATCH Route 

If you have completed the steps up to this point, try adding a route that allows you to request a different name for a specific pet. It’s up to you how you want to achieve this, but see if you are able to tweak your earlier helper method to make this possible. Once the AI suggests a new name, update the name in the database.
