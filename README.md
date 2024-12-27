

# Product Perspective

Our mobile app named "Intelli Notes", developed for Null Studios, incorporates AI and traditional note-taking into a single platform and is a standalone, self-contained system designed to help the way users capture, enhance, and organize their ideas and hence, notes.
Most people (for example: students, creative writers and even office workers) when using a standard notes app need to constantly refer to other sources like Chat GPT, Grammarly, Google etc. often making the process very time consuming. Hence, to overcome this time-consuming hurdle, our mobile app, positioned as a unique solution in the market, leverages Flutter, Dart, and the GPT-3.5 API to integrate advanced AI capabilities seamlessly into the note-taking process. The app will allow the user to enhance its text by incorporating features such as title generation, synonym suggestions, paraphrasing, word count etc. Additionally, it will prioritize user security by providing the option to lock notes, ensuring sensitive information remains private.

The mobile app’s role, tailored for those in academic or creative fields, will vary according to the user, from a note-taking assistant to a creative idea provider. In conclusion, our app aims to transform your note-taking experience, empowering you to focus on your ideas without the hassle of constant external references. It will provide a personal user-friendly space for those seeking to make their note taking process easier than ever.

Below is an overview of how the app will function and its features:


<img width="708" alt="Screenshot 2024-03-03 at 11 06 54 PM" src="https://github.com/ushnamalikk/intellinotes/overview.png">

## Setup

### Prerequisites

-   Ensure you have Flutter installed on your system. You can find instructions on how to install Flutter [here](https://docs.flutter.dev)
-   Obtain an API key for the GPT-3.5 API from OpenAI. Instructions on obtaining the API key can be found [here](https://openai.com/api/).

### Installation

1.  Clone this repository to your local machine.
    
  
    
    `git clone https://github.com/tanzeela-aijaz/SE-Project-Group-17.git` 
    
2.  Navigate to the project directory.
    
    `cd SE-Project-Group-17/MobileApp` 
    
3.  Create a file named `.env` in the project root and add your GPT-3.5 API key.
    
    `GPT_API_KEY=your-api-key-goes-here` 
    
4.  Run the following command to install dependencies.
    
    `flutter pub get` 
    
5.  Connect your mobile device or emulator.
6.  Run the app.

    `flutter run` 
    

## Functionality


## Description of Directory Files

## 1. Main Screen

This file contains the implementation of the `GetStartedPage` widget, which serves as the introductory screen of the application when the users open the application for the first time.It provides users with information about the app and encourages them to get started.

### Key Features
1. **Brand Name Display**: Displays the brand name "Intelli Notes" at the top of the screen, providing a recognizable identity for the application.
2. **Illustrative Icon**: Includes an illustrative icon of a pencil using FontAwesomeIcons to visually represent note-taking functionality.
3. **Colorful Background**: Utilizes a colorful background with varying shades to create visual interest and enhance the overall aesthetics of the screen.
4. **Informative Text**: Provides informative text sections to inform users about the purpose and features of the application.
5. **Get Started Button**: Includes a prominent "Get Started" button to prompt users to proceed to the main functionality of the app.

### Implementation Details:
- **UI Design**: Follows a minimalist design approach with bold typography and vibrant colors to capture users' attention and create an engaging user experience.
- **Iconography**: Uses the FontAwesome icon library to incorporate visually appealing icons for the pencil illustration.
- **Navigation**: Implements navigation to the HomeScreen upon tapping the "Get Started" button using Navigator.pushReplacement.

### UI/UX Components:
- **Text Widgets**: Utilizes Text widgets with custom styling to display brand name, informative text, and button text.
- **Container Widgets**: Uses Container widgets with padding and decoration to create visual sections and enhance readability.
- **Gesture Detector**: Incorporates GestureDetector to enable tapping functionality on the "Get Started" button, providing interactivity for user engagement.

### Usage:
The GetStartedPage widget serves as the initial screen for introducing users to the application. It can be navigated to from other screens or set as the default route in the application to provide a seamless onboarding experience for new users.

## 2. Home Screen

This file contains the implementation of the `HomeScreen` widget, which serves as the home screen of the application. It allows users to view their notes, add new notes, search for specific notes, and perform various actions on their notes such as locking, deleting, and accessing settings.

### Key Features
1. **Note Display**: Displays a list of notes retrieved from Cloud Firestore in a grid view format.
2. **Search Functionality**: Allows users to search for specific notes by title or content.
3. **Note Creation**: Provides an option to add new notes by navigating to the `CreateNote` screen.
4. **Note Viewing**: Enables users to view individual notes in detail by tapping on their respective note cards.
5. **Password Protection**: Allows users to lock notes with a password for added security.
6. **Note Management**: Provides options to delete notes and access settings for further customization.
7. **Real-time Updates**: Utilizes `StreamBuilder` to fetch notes from Firestore and update the UI in real-time e.g., by reflecting changes in list of notes and search query.

### Implementation Details:
- **State Management**: The `HomeScreen` is implemented as a stateful widget to manage the real-time list of notes and filtered notes.
- **UI Design**: Follows Material Design principles with custom styles and widgets for a cohesive user experience.
- **Data Handling**: Interacts with Cloud Firestore for storing and retrieving notes data.
- **Password Dialog**: Displays an AlertDialog for users to enter a password to unlock locked notes.
- **Error Handling**: Displays error messages using `SnackBar` in case of incorrect passwords or data fetching errors.

### UI/UX Components:
- **Grid View**: Utilizes a `GridView` layout to display notes in a grid format, optimizing screen space.
- **Note Card**: Each note card in the grid view displays the title, creation date, body preview, and word count of the corresponding note.
- **Action Buttons**: Includes visually appealing buttons with appropriate icons and text for adding notes, accessing settings, and performing actions like locking and deleting notes.
- **Gesture Detection**: Incorporates `GestureDetector` to enhance user interaction, allowing users to dismiss the keyboard with a tap outside text fields.
- **Form Fields**: Customized text fields for entering search queries and passwords.
- **Validation Feedback**: Displays validation messages for search queries and password inputs.

### Security and Data Handling:
- **Firestore Integration**: Interacts securely with Cloud Firestore to store and retrieve notes data, ensuring user privacy and data integrity.
- **Password Protection**: Implements password locking functionality using cryptographic operations (`crypto.dart`) and persistent storage (`shared_preferences.dart`) for enhanced security.

### Dependencies:
- `flutter/material.dart`: Flutter framework for building UI components.
- `cloud_firestore.dart`: FlutterFire plugin for interacting with Cloud Firestore.
- `google_fonts.dart`: Package for using Google Fonts in Flutter applications.
- `noteclass.dart`: Custom class for representing notes.
- `createnote.dart`: Screen for creating new notes.
- `noteview.dart`: Screen for viewing individual notes.
- `deletednotescreen.dart`: Screen for viewing deleted notes.
- `lockednotescreen.dart`: Screen for accessing locked notes.
- `settingscreen.dart`: Screen for accessing application settings.
- `notecard.dart`: Widget for displaying individual note cards.
- `appstyle.dart`: Custom styles for the application.
- `shared_preferences.dart`: Package for storing key-value pairs persistently on the device.
- `crypto.dart`: Package for cryptographic operations.

### Usage:
The `HomeScreen` widget is typically used as the initial screen of the application. It can be navigated to from other screens or set as the default route in the application.



## 3. Note View
`NoteView` is an essential Flutter class in the IntelliNotes app, enabling users to interact with their notes in detail, including viewing, editing, and deleting functionalities.

### Key Features
- **Dynamic Content**: Displays note content from Cloud Firestore in real-time.
- **Edit and Delete**: Offers in-view editing and deletion of notes.
- **Locking Mechanism**: Allows notes to be locked for added security.
- **Word Count**: Provides a real-time count of the words in a note.
- **Custom Note Actions**: Features a `NoteOptions` widget for advanced text manipulation.

### Technical Highlights
- **User Input**: Manages input through `TextEditingController`.
- **Data Fetching**: Uses `StreamBuilder` for real-time data updates.
- **Material Design**: Ensures a consistent and intuitive UI.

### Security and Data Handling
- **Secure Storage**: Leverages Flutter Secure Storage for sensitive data.
- **Firestore Integration**: Utilizes Cloud Firestore for efficient data storage and retrieval.

## 4. Deleted Notes Screen

The `DeletedNotesScreen` class displays a list of notes that have been marked as deleted. It allows users to either restore these notes to their original state or permanently delete them.

### Features

- **StreamBuilder Integration**: Fetches deleted notes in real-time from Firestore using `StreamBuilder`.
- **Interactive List**: Uses `ListView.separated` to display each deleted note with options to restore or delete permanently.
- **Restore Functionality**: Each note can be restored to the main notes collection with a single tap.
- **Permanent Deletion**: Notes can also be permanently deleted from the database.

### UI Components

- **Card and ListTile**: Each note is presented in a card with the note's title and a preview of its content.
- **Action Icons**: Includes icons for restoring notes and deleting them permanently, with tooltips for clarity.

## 5. Note Detail Screen

`NoteDetailScreen` inside deletednotescreen file is designed to display the full content of a note, whether it's from the active notes or deleted notes. It supports viewing but not editing.

### Layout

- Displays the note's title and full content.
- Utilizes `Scaffold`, `Padding`, and `SingleChildScrollView` for layout.

### Styling

- The background and app bar colors are matched for aesthetic consistency.
- Text styling emphasizes the note's title and content for readability.

### Navigation

- Provides a back button in the app bar for easy navigation back to the previous screen.

These classes contribute to the IntelliNotes app by managing the lifecycle of deleted notes and providing detailed views of individual notes.

## 6. Locked Notes Screen 

The `LockedNotesScreen` class showcases the functionality within the IntelliNotes app for displaying notes that have been locked by the user for added security.

### Features

- **Secure Note Viewing**: Lists all notes that have been locked by the user, ensuring sensitive information is kept private.
- **StreamBuilder Integration**: Uses `StreamBuilder` with Firestore to dynamically display locked notes in real-time.
- **User Interaction**: Allows users to interact with locked notes, offering options to unlock or permanently delete them.

### UI Design

- **Material Design**: Follows Material Design principles for a cohesive look and feel that matches the rest of the app.
- **Adaptive Layout**: Implements a `GridView` layout that adapts to different screen sizes and orientations.

### Navigation

- **WillPopScope**: Utilizes `WillPopScope` to manage app navigation, ensuring a smooth user experience when exiting the locked notes view.

### Custom Widgets

- **NoteCardWidget**: A custom widget that displays a summary of each locked note, including title and content preview.
- **NoteDetailView**: Provides a detailed view of a selected locked note, with options for further actions like editing or unlocking.

### Security and Accessibility

- **Firestore Security**: Interacts with the `LockedNotes` collection in Firestore, which is designed to store notes securely.
- **Enhanced User Control**: Offers users full control over their locked notes, including options to restore or permanently remove them.

This class is integral to the IntelliNotes app, enhancing note security and user privacy by segregating sensitive notes and providing a dedicated interface for their management.

## 7. Settings Screen

`SettingsScreen` is a crucial component of the app, allowing users to set or change a password for accessing locked notes, enhancing security and personal privacy.

### Key Functionalities

- **Password Management**: Enables users to securely set or change their password for locked notes.
- **Form Validation**: Incorporates form validation to ensure password requirements are met, including length and confirmation match.

### Implementation Details

- **Shared Preferences**: Utilizes `SharedPreferences` for storing the hashed password securely on the device.
- **Security Practices**: Employs `sha256` hashing for password storage, ensuring that passwords are not stored in plain text.
- **User Feedback**: Provides immediate feedback via `SnackBar` upon successful password set/change.

### User Interface

- **Form Fields**: Includes text fields for new password input and confirmation, with obscured text for privacy.
- **Validation Feedback**: Displays validation messages for password length and match criteria.
- **Action Button**: Contains an elevated button to submit the password change or set action based on the current state.

### State Management

- **Initialization**: Checks if a password is already set on initialization and updates UI accordingly.
- **State Updates**: Dynamically updates the UI to reflect the current state of password set/change.

This screen plays a vital role in maintaining user security within the app, providing a straightforward and secure way to manage access to locked notes.

## 8. Create Note File

The `createnote.dart` file enables users to create and save new notes within the mobile application. It offers various features for note management and customization.

### Key Functionalities

- Users can input a title and content for a new note.
- Automatic timestamping of notes with the current date and time.
- Dynamic word count update as the user types the note content.
- Creating and saving new notes.
- Updating word count in real-time.
- Handling note deletion and discard actions.

### Dependencies

Ensure all necessary dependencies are installed and imported:

- flutter/material.dart: Flutter framework for building UI.
- flutter/services.dart: Flutter services for platform integration.
- myapp/style/appstyle.dart: Custom app styles.
- intl/intl.dart: Internationalization support for formatting date and time.
- myapp/Classes/noteclass.dart: Custom class for note management.
- myapp/screens/notesave.dart: Screen for saving the note.
- myapp/screens/notedelete.dart: Screen for deleting the note.
- myapp/screens/note_options.dart: Widget for note manipulation options.
 
 
### Implementation

The implementation includes a Flutter StatefulWidget called CreateNote along with its corresponding state class `_CreateNoteState`. Various Flutter widgets like `TextField`, `AppBar`, `AlertDialog` are utilized to create the user interface and handle user interactions.

#### Details

- The CreateNote widget manages the creation of new notes.
- Text editing controllers are used to handle user input for title and content.
- Date and color generation are automated using Dart libraries.
- Word count is dynamically updated through state management.
- Dialogs are employed to confirm note deletion and discard actions.

### State Management

State management is achieved using Flutter's built-in `setState()` method to update the widget's state whenever there are changes in user input or other data.

### User Interface

The user interface consists of:

- App bar with title and delete icon.
- Title and content input fields.
- Display for current date and time.
- Word count indicator.
- Option for note manipulation through custom widgets.

### Styling

The user interface is styled using custom app styles defined in the AppStyle class. Various text styles, colors, and layouts are used to create a visually appealing and user-friendly note-taking environment.

### Instructions

1.	Run the application on a compatible Flutter environment.
2.	Navigate to the "Add a New Note" screen.
3.	Input a title and content for the note.
4.	Optionally, utilize note manipulation options provided.
5.	Save the note or discard changes as needed.

## 9. Save Note File

The `notesave.dart` file provides functionalities for managing notes within the application. It includes methods for saving new notes and updating existing ones in a Firestore database.

### Features

- Save new notes with title, content, creation date, and color ID.
- Will save new note if either title or content is written.
- Update existing notes with new title and content.

### Dependencies

Ensure that the following dependencies are imported into your Flutter project:

- `flutter/material.dart`: Flutter framework for building UI.
- `cloud_firestore.dart`: Firestore package for accessing Firestore database.

### State Management

This code ensures that new notes are saved only if either the title or the body is not empty. This is achieved by checking if either the title or body is not empty before saving the note to the Firestore database.

### Implementation

**Save Note Function (`saveNote()`)**

The `saveNoteIfNotEmpty` function is responsible for saving a new note to the Firestore database. It takes parameters for the note's title, body, creation date, and color ID. Before saving the note, it checks if either the title or the body is not empty. If either is not empty, the note is saved to the Firestore database. Otherwise, it does not save the note.

**Update Note Function (`updateNote`)**

The `updateNote` function is used to update an existing note in the Firestore database. It requires the document ID of the note to be updated, along with the new title and content. Upon invocation, it updates the specified note with the provided title and content.

**Conditional Check for Saving Note**

The conditional check `if (title.isNotEmpty || body.isNotEmpty)` ensures that a new note is saved only if either the title or the body is not empty. This prevents saving empty notes into the database.

**Error Handling**

Error handling is implemented using `then()` and `catchError()` methods. If an error occurs during the saving or updating process, it is caught and an error message is printed to the console. This helps in identifying and troubleshooting any issues that may arise during note management operations.

## 10. Note Delete File
The `notedelete.dart` file contains utility functions for confirming and executing the deletion of notes. These functions are primarily used in conjunction with the `AlertDialog` widget to prompt the user for confirmation before deleting a note.

### Features:
1. **Confirmation Dialog**: Displays an AlertDialog to confirm the deletion of a note, ensuring that the user wants to proceed with the deletion.
2. **Move Note to DeletedNotes Collection**: Moves the selected note from the "Notes" collection to the "DeletedNotes" collection in Firestore before deleting it.
3. **Delete Note Card**: Deletes the note from the "Notes" collection after it has been successfully moved to the "DeletedNotes" collection.

### Implementation Details:
- **confirmDelete**: Creates an AlertDialog with options to cancel or delete the note.
- **moveNoteToDeleted**: Retrieves the note from Firestore, moves it to the "DeletedNotes" collection, and then calls `deleteNoteCard`.
- **deleteNoteCard**: Deletes the note from the "Notes" collection and closes the AlertDialog and the current screen.


## 11. AppStyle Class

### Color Palette:
- **Main Color: mainColor (0xFF000000) - Used as the primary color for background and foreground elements.
- **Accent Color: accentColor (0xFF0065FF) - Used as the accent color for interactive elements such as buttons and links.
- **Background Color: bgColor (0xFFe2e2ff) - Used as the background color for screens and containers.
- **Cards Color Palette: The cardsColor list provides a selection of colors for individual cards or components within the application. Each color is represented as a hexadecimal value.

### Text Styles:
- **Main Title**: mainTitle - Defines the text style for main titles or headings with Roboto font, bold weight, and a font size of 18.0.
- **Main Content**: mainContent - Defines the text style for main content or body text with Nunito font, normal weight, and a font size of 16.0.
- **Date Title**: dateTitle - Defines the text style for date titles or captions with Roboto font, medium weight, and a font size of 13.0.

### Usage:
The AppStyle class can be imported and used across various screens and widgets within the application to maintain a consistent visual appearance and typography. By accessing the predefined colors and text styles, developers can ensure a cohesive design language throughout the app, enhancing readability and user experience.


## 12. API Service (api_service.dart)

## Description
The `api_service.dart` file encapsulates functionality related to interacting with the GPT-3.5 API. It provides methods for paraphrasing, summarizing, and generating titles for text inputs using AI capabilities. This service facilitates the integration of AI-powered features into the Flutter note-making application.

## Features
- **Paraphrase Text**: Utilizes the GPT-3.5 API to paraphrase input text.
- **Summarize Text**: Summarizes input text using the GPT-3.5 API.
- **Generate Title**: Generates a title for input text based on AI analysis.

## 13. Note Options (note_options.dart)

## Description
The `note_options.dart` file defines a Flutter widget responsible for displaying options to manipulate notes within the note-making application. It includes functionalities such as paraphrasing, summarizing, generating titles, and copying text to the clipboard. These options are seamlessly integrated into the application's user interface to enhance user experience and productivity.

## Features
- **Paraphrase Text**: Allows users to paraphrase the content of notes.
- **Summarize Text**: Provides a summary of note content.
- **Generate Title**: Automatically generates titles for notes.
- **Copy Text**: Enables users to copy note content to the clipboard.

## Usage

### Paraphrase Text
- **Button Icon**: A circular button with an icon representing paraphrasing functionality (e.g., an autorenew icon).
- **Interaction**: Users tap the paraphrase button.
- **Task Execution**: Upon tapping the button, the content of the note is sent to the AI service for paraphrasing.
- **Response**: Users receive a dialog with the paraphrased text or an error message if the operation fails.
- **Actions**:
  - **Replace**: Users can replace the content of the note with the paraphrased text.
  - **Copy**: Users can copy the paraphrased text to the clipboard.

### Summarize Text
- **Button Icon**: A circular button with an icon representing summarization functionality (e.g., an article icon).
- **Interaction**: Users tap the summarize button.
- **Task Execution**: Upon tapping the button, the content of the note is sent to the AI service for summarization.
- **Response**: Users receive a dialog with the summarized text or an error message if the operation fails.
- **Actions**:
  - **Replace**: Users can replace the content of the note with the summarized text.
  - **Copy**: Users can copy the summarized text to the clipboard.

### Generate Title
- **Button Icon**: A circular button with an icon representing title generation functionality (e.g., a title icon).
- **Interaction**: Users tap the generate title button.
- **Task Execution**: Upon tapping the button, the content of the note is sent to the AI service for title generation.
- **Response**: Users receive a dialog with the generated title or an error message if the operation fails.
- **Actions**:
  - **Replace**: Users can replace the title of the note with the generated title.
  - **Copy**: Users can copy the generated title to the clipboard.

### Copy Text
- **Button Icon**: A circular button with an icon representing copying functionality (e.g., a content_copy icon).
- **Interaction**: Users tap the copy button.
- **Task Execution**: Upon tapping the button, the content of the note is copied to the clipboard.
- **Feedback**: Users receive a notification confirming that the text has been copied to the clipboard.

## Contributing

We welcome contributions from the community! If you'd like to contribute to the project, please read our [contributing guidelines](https://nothing) and submit a pull request.

## License

This project is licensed under the MIT License.

## Contact

For questions, feedback, or support, please contact 25020106@lums.edu.pk | 25100208@lums.edu.pk | 25100105@lums.edu.pk | 25100256@lums.edu.pk
