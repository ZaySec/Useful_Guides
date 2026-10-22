Source: https://github.com/Densaugeo/uploadserver

# Upload
1. Startup a `Python` environment 
	1. `python -m venv .venv && source .venv/bin/activate.fish
2. Change directories to where the file you want to upload is located
	1. `cd ~/Tools
3. Start the upload server (Default Port 8000)
	1. `python -m uploadserver

# Download
- Download a File Using `wget`
	- `wget http://<host-ip>:8000/<file> -O <file>

- Download a File Using `cURL`
	- `curl -o <file> http://<host-ip>:8000/<file>