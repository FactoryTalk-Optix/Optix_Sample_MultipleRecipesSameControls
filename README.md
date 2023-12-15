# Handle multiple RecipeSchema with same UI Controls

This project demonstrates how to handle multiple recipes schema using the same UI Controls, this is particularly convenient when the production line is complex and has a lot of parameters and you want to split them in multiple pages but using just one button to apply/load

## Important note

This example contains a modified version of the `RecipeEditor` from the `TemplateLibrary` which has been adjusted to handle this specific scenario, make sure you don't have any `RecipeEditor` in your project already

## FT Optix version

This project was developed with FT Optix 1.3.X

## Instructions to replicate this project in your application

Project is ready to run as a demo but if you want to implement it in your project these are the steps you need to perform

1. Make sure you have a Database where to store your recipes (`EmbeddedDatabase` in this example)
1. Create as many `RecipeSchema` as you need (using the wizard or by creating them in the `Recipes` folder), all schemas **must** use the same Database. The name of such schemas is not critical and can be any valid string.
1. Copy the `UI > MainWindow` content to any page of your project where you want to manage your recipes (this is the common part that will handle the whole logic, there should be just a single instance of these objects, typically in the header of your recipes management page)
1. After pasting the page content select `CommonParameters > RecipesEditorMulti` and create as many `RecipeSchemaX` as you need by copy-pasting an existing one (where `X` is an incremental number). You can also delete the ones you are not using (in this example we are using 4 of them)
    - You should see:
        - `RecipeSchema1`
        - `RecipeSchema2`
        - ...
1. Link each `RecipeSchemaX` variable you copy-pasted to the corresponding `RecipeSchema` in your project
    - You should see:
        - `RecipeSchema1` -> `RecipeSchema1`
        - `RecipeSchema2` -> `RecipeSchema1`
        - ...
1. Move to `UI > Screens > ParametersA` and copy the modified `RecipesEditor` as many time you need in your project (these can be in different pages, sections or anywhere in your project)
1. For each `RecipesEditor` you pasted in your project, select it and assign a unique `RecipeSchema` in the properties list
1. For each `RecipesEditor` you pasted in your project, select it, and with a right click perform `Execute Setup` to generate the page content from the RecipeSchema
1. Done! You can now run the application and use the header to manage all the different `RecipeSchemas` at once

## Disclaimer

Rockwell Automation maintains these repositories as a convenience to you and other users. Although Rockwell Automation reserves the right at any time and for any reason to refuse access to edit or remove content from this Repository, you acknowledge and agree to accept sole responsibility and liability for any Repository content posted, transmitted, downloaded, or used by you. Rockwell Automation has no obligation to monitor or update Repository content

The examples provided are to be used as a reference for building your own application and should not be used in production as-is. It is recommended to adapt the example for the purpose, observing the highest safety standards.
