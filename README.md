# Ruby Brush Up Practice App

This Rails application was created to brush up on Ruby on Rails fundamentals, specifically focusing on the scaffold command and understanding how the generated components work together.

## Project Overview

This project follows along with Ruby on Rails tutorial Episode 1, demonstrating the scaffold command and exploring the relationships between different parts of a Rails application.

## Dependencies Setup

- **Ruby 3.1.4** - Installed via rbenv
- **Rails 7.2.2.2** - Latest stable version
- **Bundler 2.6.9** - Gem dependency management

## Scaffold Command Analysis

The scaffold command in Rails is a powerful generator that creates a complete MVC (Model-View-Controller) structure for a resource. Here's how the generated parts relate to each other:

### Generated Components

1. **Model** (`app/models/`)
   - Defines the data structure and business logic
   - Includes validations and associations
   - Handles database interactions through ActiveRecord

2. **Controller** (`app/controllers/`)
   - Handles HTTP requests and responses
   - Contains actions (index, show, new, create, edit, update, destroy)
   - Coordinates between models and views
   - Implements CRUD operations

3. **Views** (`app/views/`)
   - Templates for displaying data to users
   - HTML with embedded Ruby (ERB)
   - Forms for user input
   - Partial views for reusable components

4. **Routes** (`config/routes.rb`)
   - Maps URLs to controller actions
   - Defines RESTful routes
   - Enables RESTful resource routing

5. **Database Migration** (`db/migrate/`)
   - Creates the database table structure
   - Defines columns, data types, and constraints
   - Version-controlled database schema changes

6. **Tests** (`test/`)
   - Model tests for business logic
   - Controller tests for request handling
   - Integration tests for user workflows

### How They Work Together

```
User Request → Routes → Controller → Model → Database
                    ↓
                View ← Controller ← Model ← Database
                    ↓
                Response to User
```

1. **Request Flow**: User makes a request → Routes determine which controller action to call → Controller processes the request
2. **Data Access**: Controller interacts with the Model → Model queries/updates the Database
3. **Response Generation**: Model returns data to Controller → Controller renders appropriate View → View generates HTML response

### Key Relationships

- **Controller ↔ Model**: Controllers use models to access and manipulate data
- **Controller ↔ View**: Controllers pass data to views and determine which view to render
- **Model ↔ Database**: Models use ActiveRecord to interact with the database
- **Routes ↔ Controller**: Routes map URLs to specific controller actions
- **Views ↔ Model**: Views can access model data passed from controllers

## Getting Started

1. Clone the repository
2. Run `bundle install` to install dependencies
3. Run `rails db:migrate` to set up the database
4. Run `rails server` to start the development server
5. Visit `http://localhost:3000` in your browser

## Learning Objectives

- Understanding Rails scaffold command
- Exploring MVC architecture in Rails
- Learning how Rails components interact
- Practicing CRUD operations
- Understanding RESTful routing

## Tutorial Reference

This project follows Ruby on Rails tutorial Episode 1, focusing on:
- Setting up the development environment
- Using the scaffold command effectively
- Understanding the generated code structure
- Learning Rails conventions and best practices
