# Example: Starting a New Project the Right Way

The full setup sequence, applied to a small realistic project: a script that fetches weather data from an API.

## Step 1: Create the project folder

```bash
mkdir weather-check && cd weather-check
```

## Step 2: Create a virtual environment

```bash
python -m venv .venv
```

## Step 3: Activate it

```bash
# macOS / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

Your prompt should now show `(.venv)` — that's your confirmation it's active.

## Step 4: Install what you need

```bash
pip install requests
```

## Step 5: Freeze your dependencies

```bash
pip freeze > requirements.txt
```

```
# requirements.txt
requests==2.31.0
certifi==2024.2.2
charset-normalizer==3.3.2
idna==3.6
urllib3==2.2.1
```

Note that `pip freeze` captures `requests`' own dependencies too — that's expected and correct.

## Step 6: Write the script

```python
# main.py
import requests

def get_weather(city):
    response = requests.get(
        "https://api.example.com/weather",
        params={"city": city},
    )
    response.raise_for_status()
    return response.json()

if __name__ == "__main__":
    print(get_weather("Portland"))
```

## Step 7: Someone else clones the project

This is the entire reason the steps above matter — anyone else can reproduce your exact environment:

```bash
git clone <repo-url>
cd weather-check
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python main.py
```

## Why Every Step Earns Its Place

Skipping the virtual environment means `pip install` writes to your global Python — fine for a five-minute experiment, a real problem the moment you have two projects that need different package versions. See the [project setup diagram](../diagrams/project-setup-flow.md) for this as a flowchart.
