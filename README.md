# Seminal Recipe
Seminal Recipe, a Drupal Recipe designed to streamline the setup of your Drupal site. Seminal simplifies the process of building and managing your Drupal site by providing all the essential blocks, content types, views, and a pre-configured theme, eliminating the need for extensive component or theme development.

## What is Seminal Recipe?
Seminal Recipe is a comprehensive Drupal Recipe that can be applied to your Drupal 10 or 11 installation. This recipe provides a fully integrated set of blocks, content types, views, and a ready-to-use theme, allowing you to get your site up and running quickly with minimal configuration.

## Key Features

- Pre-configured Blocks: Ready-to-use blocks for various site elements, making it easy to organize and display content.
- Custom Content Types: A range of content types tailored to fit common use cases, ensuring effective content management.
- Pre-built Views: Out-of-the-box views to display and filter content according to your needs.
- Integrated Theme: A well-designed, responsive theme included, so you don’t need to spend time on theme development or customization.

## Getting Started

### Fresh Installation:

- Begin with a fresh Drupal 10 or 11 setup.Follow the standard installation process to set up your base Drupal site.
- Make sure your Drupal site is set up.

### Apply the Seminal Recipe:

- For Composer to understand Seminal Recipe install-type, you need to require the Composer Installer Extender package.

```bash
composer require oomphinc/composer-installers-extender:2.0.1
```

- This package lets you define new install-types for Composer so it understands where to place them in the file system when it encounters them.

- Next, you need to add two entries in `composer.json` for an install-type and its path:

- In case of `docroot/`

```
"installer-types": ["drupal-recipe"],
"installer-paths": {
 "docroot/recipes/{$name}": [
   "type:drupal-recipe"
 ]
}
```

or

- In case of `web/`

```
"installer-types": ["drupal-recipe"],
"installer-paths": {
    "web/recipes/{$name}": [
        "type:drupal-recipe"
    ],
}
```

- When you add a Recipe with Composer, it will automatically be placed into the recipes/ directory of your project, just like modules or themes.

- Although Drupal.org doesn’t yet have an official spot for Recipe projects, you can still use Composer to manage where your Recipe is located. Simply create a repository on GitLab or GitHub for your Recipe and add the repository location to the repositories section of your `composer.json` file:

```
{
 "type": "vcs",
 "url": "https://github.com/mvpsatyam/seminal_recipe"
}
```

- Since you configured Composer to recognize what a Recipe is, and where yours is located, you can pull it into your project:

```bash
composer require mvpsatyam/seminal_recipe
```

- Recipes are applied using Drupal core's PHP script. To do this, run the following command from your Drupal root directory. This could be in the (web, docroot, or any other folder) where Drupal is installed:

```bash
php core/scripts/drupal recipe recipes/seminal_recipe
```

- This will automatically configure blocks, content types, views, and the theme.

### Configuration:

- After applying the recipe, navigate to the site configuration to review and adjust settings as needed.
- Explore the pre-configured blocks, content types, and views to familiarize yourself with the features.

### Customization:

- Modify the content types and views to better fit your specific needs.
- Customize the theme if desired, using Drupal’s built-in theming tools.

### Content Management:

- Begin adding and managing content using the provided content types.
- Utilize the pre-built views to effectively display your content.