# 04 World Wide Web

## Core Technologies

### 1. HTML (HyperText Markup Language)
- Defines structure and content of web pages
- Uses hyperlinks to connect to other documents/resources
- Enables combining resources from different servers
- Example: Images embedded in a page can come from various web servers

### 2. URL (Uniform Resource Locator)

- Unique identifier for resources on the Internet
- Format: `protocol://hostname/path`
	- Protocol or Access Method: e.g., `http` or `https`
	- Hostname: Domain name (e.g., `www.example.com`)
	- Path: Specific resource location (e.g., `/index.html`)
- Example: `https://www.example.com/index.html`
- Can include port numbers (e.g., `:8080` for custom ports)

### 3. HTTP (HyperText Transfer Protocol)
- Governs communication between web browser (client) and web server
- HTTPS: Secure version using encryption (port 443)
- Default ports:
	- HTTP: Port 80
	- HTTPS: Port 443
- Defines request-response procedure for fetching resources

## How It Works
- **Browser-Server Interaction**:
	- Browser resolves IP address from URL's domain name
    - Sends HTTP/HTTPS request to server (port 80 or 443)
    - Server responds with requested resource (e.g., HTML file)
    - Browser fetches additional resources (e.g., images via `<img src="...">`)
	- Renders complete webpage on screen

## History and Origins

### Tim Berners-Lee
- Invented the World Wide Web in 1989 at CERN
- Motivation: Manage CERN's information overload
- Problem: Anonymous FTP servers caused network congestion
- Solution: Proposed "Information Management: A Proposal"
    - Used hypertext to reference documents by their original location
    - Reduced need for copying files, easing server load

### Theodor Holm Nelson
- Introduced "hypertext" concept in the 1960s
- Vision: Documents linked without needing to know their physical location
- Started the Xanadu Project to develop hypertext
- Influenced Berners-Lee’s implementation of hypertext/hyperlinks

## Key Concepts
- **Hypertext**: Documents linked via references (hyperlinks)
- **World Wide Web**: A network of interlinked resources, resembling a spider’s web
- **Evolution**: HTML5 enhances expressive capabilities of HTML
