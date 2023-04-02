# MVC-
# Model
class UserModel:
    def __init__(self, name, lastname, age, status):
        self.name = name
        self.lastname = lastname
        self.age = age
        self.status = status

# View
class UserView:
    def display_user(self, user):
        print("Name: ", user.name)
        print("lastname: ", user.lastname)
        print("age: ", user.age)
        print("status: ", user.status)
       

# Controller
class UserController:
    def __init__(self, model, view):
        self.model = model
        self.view = view

    def set_name(self, name):
        self.model.name = name

    def set_lastname(self, lastname):
        self.model.lastname = lastname
        
    def set_age(self, age):
        self.model.age = age
        
    def set_status(self, status):
        self.model.status = status

    def update_view(self):
        self.view.display_user(self.model)

# Usage
if _name_ == "_main_":
    # Create a user model
    user = UserModel("o", "g", "40", "single")

    # Create a view to display the user
    view = UserView()

    # Create a controller to update the user and display the view
    controller = UserController(user, view)

    # Update the user's information
    controller.set_name("o")
    controller.set_lastname("g")
    controller.set_age("40")
    controller.set_status("single")

    # Display the updated user information
    controller.update_view()
