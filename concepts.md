# Concerto CMS concepts

## Infrastructure

The heart of the CMS is an API that uses a MongoDB datasource. It is divided into 2 API endpoints: the *management API* is a read/write endpoint that drives the CMS webapp. The *publication API* is a read-only API intended for exposing the content and publishing it on your website.

The API is written in NodeJS and Express JS. The CMS webgui is an Angular 4 web application. The website can be programmed in a language of your choosing. Client libraries will be provided for the most popular platforms.

## CMS app structure

Once you login, you start off in a dashboard where you can see the sites you have access to, or create a new website. As soon as you pick the website on which you wish to continue, the app is provided into 3 different modules. Which modules available to you depend on your site role:
- Manage module (owners only)
- Develop module (owners and developers)
- Editor module (all users, only module available to editors)

### Manage module

This module allows an /owner/ to modify some general settings, add contributors or set their permissions and configure client keys for the publication API.

### Develop module

A developer can use this module to define the object models and blocks. This is an important step towards creating a well structured website.

### Editor module

This module is the real CMS module. An editor can create and modify the website content. The fields of all forms are dynamically rendered based on the given object models and blocks.

## Models, Blocks, Fields

These terms may be a bit confusing, so some explanation may help.

### Models

If you were to design a database for your website, a model would represent a table of your database. Some common models are: webpage, blogpost, menu item, etc... As you may have noticed, most of these models represent a webpage. If the "webpage" option is enabled for a model, it will automatically contain some common fields that each webpage must have: a title, meta description and most importantly a unique URL.

Each model will also enable a separate tab in the editor module, so an editor can manage all different types of content.
