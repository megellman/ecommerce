# E-commerce Back End
![license badge](https://img.shields.io/static/v1?label=license&message=MIT&color=blue)

## Technology Used 

| Technology Used         | Resource URL           | 
| ------------- |:-------------:| 
| HTML    | [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/HTML) |      |   
| Git | [git-scm.com](https://git-scm.com/)     |    
| Node.js | [nodejs.org/docs](https://nodejs.org/docs/latest-v16.x/api/) |
| MySQL | [dev.mysql.com](https://dev.mysql.com/doc/)  |
| Sequelize | [sequelize.org](https://sequelize.org/docs/v6/getting-started/)  |
| Express.js | [expressjs.com](https://expressjs.com/en/guide/routing.html)  |
    
## Description

[Visit the Deployed Site](https://megellman.github.io/ecommerce-back-end/)
    
This project is the back end for an ecommerce site where a user can view, edit, and delete products, product categories, tags, and product tags. 

I created this project using Node.js, Express.js, Sequelize and MySQL. A user is able to run get requests to get all or one specific tag, product, or category. They are also able to run post, put, and delete requests to create, update, and delete tags, products and categories. 

[Project Demo](https://watch.screencastify.com/v/xdHpaGrwuMyg15QMJ1bP)

## Table of Contents
* [Code Example](#code-example)
* [Author Info](#author-info)
* [Credits](#credits)
* [License](#license)

## Code Example

```
router.delete('/:id', async (req, res) => {
  try {
    const categoryData = await Category.destroy({
      where: {
        id: req.params.id,
      },
    });
    if(!categoryData){
      res.status(404).json({message: 'Category with that ID could not be found'});
      return;
    }
    res.status(200).json(categoryData);
  } catch(err){
    res.status(500).json(err);
  }
});
```

In the above example, I created a delete route to delete a given category based on the ID number provided in the request parameter. The .destroy method deletes an instance and the where specifies what conditions must be met in order for it to be deleted. In this example, the categoryData will be deleted where the ID is the same as the ID provided in the request parameters. If categoryData with that ID cannot be found, then the 404 error is shown with the message "Category with that ID could not be found" and the router is exited out of. If categoryData with that ID is found, then the status 200 appears and the categoryData is shown. If this all fails, then the 500 status shows along with the error message. 

## Author Info

### Megan Ellman

[LinkedIn](https://www.linkedin.com/in/megan-ellman/)

[GitHub](https://github.com/megellman)

[Portfolio](https://megellman.github.io/portfolio/)

## Credits
| Information        | Resource URL           | 
| ------------- |:-------------:| 
| Validations & Constraints    | [Sequelize Docs](https://sequelize.org/docs/v6/core-concepts/validations-and-constraints/) | 
| Destroy Method        |[Sequelize Docs](https://sequelize.org/docs/v6/core-concepts/paranoid/#deleting) | 
| Many to Many Associations        | [Sequelize Docs](https://sequelize.org/docs/v6/advanced-association-concepts/advanced-many-to-many/)       | 

## License
  
This project is covered under the MIT license. For more information please click [here](https://choosealicense.com/)

## Questions

[GitHub](github.com/megellman)

If you have any additional questions, you can reach me at meganlellman@gmail.com
