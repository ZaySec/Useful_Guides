
>[!tldr] Quickstart `python -m venv .venv && source .venv/bin/activate.fish`

**1. Create the virtual environment** Run this command to create a hidden folder named `.venv` that contains a localized Python setup:
```bash
python -m venv .venv
```

**2. Activate the environment** You must "step into" this sandbox. Notice how your terminal prompt will change after running this:
``` Bash
source .venv/bin/activate

!!!or if ur running fish!!!

source .venv/bin/activate.fish
```

**3. Install the tool's dependencies** Now that you are safely inside the virtual environment, you can install the specific packages `enum4linux-ng` needs:
``` bash
pip install -r requirements.txt
```

**4. Run the script** Because `enum4linux-ng.py` is already marked as executable in your directory (the green `.rwxr-xr-x` permissions in your screenshot), you can run it directly, or call it with Python:
``` Bash
./enum4linux-ng.py -h
```

--- 
### Exiting the Environment

When you are done using the tool and want to return to your normal terminal state, simply type:

``` Bash
deactivate
```

>[!note] : Whenever you want to use this specific tool again in the future, you just need to navigate back to this directory, run the `source .venv/bin/activate` command, and execute the script. You do not need to run the install steps again._

