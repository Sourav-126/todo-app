# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm install`
To install the all the neccessary modules in your local driver

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.


## System Design Overview

### 1. **Frontend Architecture**

#### 1.1 **Component Structure**

- **App Component**
  - The main component that initializes the application.
  - Manages the overall state and layout.
  - Uses React Router to manage navigation and URL parameters.
  - Contains the main components for adding, displaying, and searching to-do items.

- **SearchComponent**
  - Handles the search input and updates the URL parameters based on the user's query.
  - Listens for changes in the URL parameters and updates the search input field accordingly.

- **TodoComponent**
  - Renders the list of to-do items and completed items.
  - Filters the list based on the search query from the URL parameters.
  - Allows users to add, edit, delete, and mark to-do items as completed.

#### 1.2 **State Management**

- **Global State**
  - `isCompleteScreen`: A boolean flag to toggle between the to-do and completed views.
  - `allTodos`: An array storing all active to-do items.
  - `newTitle` and `newDescription`: Strings for the input fields when adding a new to-do item.
  - `completedTodos`: An array storing completed to-do items.
  - `currentEdit` and `currentEditedItem`: Variables for managing the edit state and the currently edited item.

- **Local Storage**
  - To-do items and completed items are persisted in the browser's local storage.
  - State is loaded from local storage on component mount (`useEffect`).

#### 1.3 **Routing and URL Management**

- **React Router**
  - Utilized for managing routes within the application.
  - Uses URL parameters to manage the search functionality.

### 2. **Functional Components**

- **Adding a New To-Do**
  - Users can enter a title and description to add a new to-do item.
  - The new item is added to the `allTodos` array and persisted in local storage.

- **Editing a To-Do**
  - Users can edit an existing to-do item.
  - The `currentEdit` and `currentEditedItem` states manage the editing process.
  - Updates are saved back to the `allTodos` array and local storage.

- **Deleting a To-Do**
  - Users can delete a to-do item from the list.
  - The item is removed from the `allTodos` array and local storage.

- **Completing a To-Do**
  - Users can mark a to-do item as completed.
  - The item is moved from the `allTodos` array to the `completedTodos` array and stored in local storage.
  - The completion time is recorded and displayed.


### 3. **User Interface**

- **Layout**
  - The UI includes input fields for adding to-do items, buttons for navigation, and a list display area for to-dos and completed items.
  - A search bar at the top allows filtering of the list.

- **Icons and Styling**
  - Icons from `react-icons` are used for actions like delete, edit, and complete.
  - CSS is used for styling the components and layout.

### 4. **Scalability and Future Enhancements**

- The application structure allows for easy addition of new features, such as categorizing to-dos, setting priorities, or integrating with a backend API.
- The use of URL parameters for search can be extended to other filtering or sorting options.
- The component-based architecture facilitates the reuse of components and separation of concerns, making it easier to maintain and extend the codebase.

This overview should give a clear understanding of the application's structure and functionality. You can include this in your `README.md` to provide context for the design and implementation of the system.
