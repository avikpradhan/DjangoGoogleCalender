# Django Google Calendar Integration

This Django project allows users to access their Google Calendar using OAuth2 credentials. The project consists of three views:
- `GoogleCalendarInitView`: Initiates the OAuth2 authorization flow.
- `GoogleCalendarRedirectView`: Callback view to handle the response from Google OAuth2 authorization server.
- `GoogleCalendarEventsView`: Fetches events from the user's Google Calendar.

## Project Setup

### Installation

1. Clone the repository:

    ```bash
    git clone git@github.com:avikpradhan/DjangoGoogleCalender.git
    ```

2. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Set up Google API Credentials:

    - Create a project on the [Google Cloud Console](https://console.cloud.google.com/).
    - Enable the Google Calendar API.
    - Create OAuth 2.0 credentials and download the JSON file.
    - Save the JSON file as `client_secret.json` in the project root.

4. Apply database migrations:

    ```bash
    python manage.py migrate
    ```

5. Run the development server:

    ```bash
    python manage.py runserver
    ```

## Usage

1. Open your browser and navigate to `http://localhost:8000/api/v1/calendar/init/`.

2. Authorize the application to access your Google Calendar.

3. Once authorized, you will be redirected to `http://localhost:8000/api/v1/calendar/events/`, and the fetched events will be displayed.

## Important URLs

- **Initiate OAuth Flow:** `http://localhost:8000/api/v1/calendar/init/`
- **OAuth Callback:** `http://localhost:8000/api/v1/calendar/redirect/`
- **Fetch Calendar Events:** `http://localhost:8000/api/v1/calendar/events/`

## Notes

- Ensure that your Google API credentials (`client_secret.json`) are correctly configured.
- Make sure to handle security considerations and do not expose sensitive information in production.