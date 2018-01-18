# Item Catalog Web App
This web app is a project for the Udacity [FSND Course](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004).

## About
This project is a RESTful web application utilizing the Flask framework which accesses a SQL database that populates categories and their items. OAuth2 provides authentication for further CRUD functionality on the application. Currently OAuth2 is implemented for Google Accounts.

## In This Repo
This project has one main Python module `catalog.py` which runs the Flask application. A SQL database is created using the `database_setup.py` module and you can populate the database with test data using `lotsofitems.py`.
The Flask application uses stored HTML templates in the tempaltes folder to build the front-end of the application. CSS/JS/Images are stored in the static directory.

## How to Run?

### PreRequisites
  * [Python ~2.7](https://www.python.org/)
  * [Vagrant](https://www.vagrantup.com/)
  * [VirtualBox](https://www.virtualbox.org/)
  
### Setup Project:
  1. Install Vagrant and VirtualBox
  2. Download or Clone [fullstack-nanodegree-vm](https://github.com/udacity/fullstack-nanodegree-vm) repository.
  3. Find the catalog folder and replace it with the content of this current repository, by either downloading or cloning it from
  [Here](https://github.com/david-singh/item-catalog).

### Launch Project
1. Launch the Vagrant VM (`vagrant up`)
2. Log into Vagrant VM (`vagrant ssh`)
3. Navigate to `cd/vagrant` as instructed in terminal
4. The app imports requests which is not on this vm. Run sudo pip install requests
5. Setup application database `python /item-catalog/database_setup.py`
6. *Insert fake data `python /item-catalog/lotsofitems.py`
7. Run application using `python /item-catalog/catalog.py`
8. Access the application locally using http://localhost:5000

## JSON Endpoints
The following are open to the public:

Catalog JSON: `/catalog/JSON`
    - Displays the whole catalog. Categories and all items.

Categories JSON: `/catalog/categories/JSON`
    - Displays all categories

Category Items JSON: `/catalog/<path:category_name>/items/JSON`
    - Displays items for a specific category

Category Item JSON: `/catalog/<path:category_name>/<path:item_name>/JSON`
    - Displays a specific category item.
