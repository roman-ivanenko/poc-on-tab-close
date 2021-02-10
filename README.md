# POC on Browser Window or Tab Close

## Requirements

The requirements is the following:

- The session management feature shall terminate (invalidate) the user backend session whenever the user closes the last web browser window or tab of the application <u>without explicitly logging out</u>.
- If the user opens the page again using URL, bookmark, or history in the browser, it should be redirected to the login screen. So, the user cannot re-open any page of the application without Login procedure.

## Solution

- Register JavaScripr event handler for "close tab/window” functionality (JS event `beforeunload`).
- Call server-side Logout API.
- Optionaly: count opened tabs to call Logout API only when the last web browser window or tab of the application is closed.
- Do not call Logout API if the user already explicitly signed out.

## POC

### 1. Open `index.html` Page in a Web Browser

You do not need any backend. Just open the `index.html` page in your web browser directly from the file system.

![Open the Page](images/00_POC-on-Tab-close_Open-the-page.png)


### 2. Put breakpoint

![Put breakpoint](images/01_POC-on-Tab-close_Put-breakpoint.png)


### 3. The event intercepted

![The event intercepted](images/02_POC-on-Tab-close_Tab-close-event-intercepted.png)


### 4. Paused in Debugger

![Paused in Debugger](images/03_POC-on-Tab-close_Paused-in-Debugger.png)


### 5. Resume Script Execution

![Resume Script Execution](images/04_POC-on-Tab-close_Resume-script-execution.png)
