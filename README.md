This WordPress shortcode provides a discussion feature for projects assigned to logged-in users. The shortcode [project_discussion] displays a list of projects assigned to the logged-in user, allowing them to open a chat-like interface for discussions. The discussions are stored as WordPress comments.

Features
Displays projects assigned to the logged-in user (based on a custom meta field).
Provides a real-time discussion interface with a pop-up chat box.
Fetches existing comments dynamically when a user selects a project.
Allows users to post messages which are stored as WordPress comments.
Styled UI with hover effects and animations.
Shortcode Usage
Use the following shortcode to embed the project discussion section on any page or post:


[project_discussion]

How It Works
1. Shortcode Registration (project_discussion_shortcode)
Checks if the user is logged in. If not, it displays a message requiring login.
Retrieves all projects assigned to the logged-in user by querying posts of type project where the client_portal_user meta field matches the current user ID.
Displays a list of project names as clickable cards.
Implements a chat pop-up UI where users can view and send messages related to a project.
2. JavaScript Functions
openChat(projectID, projectName)

Opens the chat window for a selected project.
Sets the project ID and title in the chat UI.
Fetches existing comments for the selected project.
closeChat()

Closes the chat window.
fetchComments(projectID)

Makes an AJAX request to retrieve all comments related to the selected project.
sendMessage()

Sends a new message via AJAX, storing it as a comment in WordPress.
After a successful message post, it reloads the chat messages.
3. AJAX Endpoints
The plugin registers two AJAX handlers for fetching and posting comments.

Fetch Project Comments (fetch_project_comments)
Retrieves comments for a given project using get_comments().
Outputs the comments inside the chat window.
Post Project Comment (post_project_comment)
Takes user input from the chat box.
Creates a WordPress comment under the selected project post.
Associates the comment with the logged-in user and marks it as approved.
4. Styling
The UI is designed with a clean look, using shadows and animations.
The chat window appears as a floating box at the bottom-right.
Messages are displayed in a conversational style.
Installation & Usage
Copy the code into your functions.php file or create a custom plugin.
Use the [project_discussion] shortcode on any page.
Ensure WordPress comments are enabled for your project post type.
Assign users to projects using the client_portal_user(change it according to your name) meta field.
This feature provides a simple and effective way for clients to discuss project details directly within WordPress! 🚀
