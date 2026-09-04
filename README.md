# Dynamic Weather Alert Automation

An n8n automation workflow that accepts a city name through a form, fetches live weather data from WeatherAPI, validates user input, handles API errors, and sends user-friendly Telegram alerts.

## Features

- Dynamic city input using an n8n Form
- Live weather data from WeatherAPI
- Telegram weather notifications
- Empty-input validation
- Invalid/nonexistent city error handling
- Separate success and error branches
- User-friendly error messages
- Reusable n8n workflow
- Security-safe placeholders for public GitHub use

## Workflow Logic

1. User enters a city in the Weather Checker form.
2. The IF node checks whether the city field is empty.
3. If empty:
   - Sends: `Please enter a valid city`
4. If a city is provided:
   - WeatherAPI is called using the entered city.
5. If WeatherAPI returns valid weather data:
   - Weather details are extracted.
   - A Telegram weather message is created and sent.
6. If WeatherAPI cannot find the location:
   - The API error branch is used.
   - Sends: `City not found. Please enter a valid city.`

## Main Nodes

- Weather Form Input
- IF
- Fetch Weather Data
- Extract Weather Details
- Build Telegram Message
- Send Weather Alert
- Build Invalid Input Message
- Send Invalid Input Alert
- Build API Error Message
- Send API Error Alert

## Requirements

Before using this workflow, you need:

- n8n
- WeatherAPI account and API key
- Telegram Bot
- Telegram Chat ID

## Setup

### 1. Import the Workflow

Import:

`dynamic-weather-alert-workflow.json`

into your n8n instance.

### 2. Configure WeatherAPI

Open the `Fetch Weather Data` node.

Replace:

`YOUR_WEATHERAPI_KEY`

with your own WeatherAPI key.

Do not publish your real API key.

### 3. Configure Telegram

Create or select your own Telegram credential in each Telegram node.

Replace:

`YOUR_TELEGRAM_CHAT_ID`

with your own Telegram Chat ID.

Configure the Telegram nodes:

- Send Weather Alert
- Send Invalid Input Alert
- Send API Error Alert

Do not expose your Telegram Bot Token or Chat ID publicly.

## Test Cases

The workflow was tested with three main scenarios:

### Valid City

Example:

`Kochi`

Result:

Weather information is sent to Telegram.

### Empty Input

Result:

`Please enter a valid city`

### Invalid / Nonexistent City

Example:

`xyzabc12345`

Result:

`City not found. Please enter a valid city.`

## Security

This public workflow does not contain real:

- WeatherAPI keys
- Telegram Bot Tokens
- Telegram Chat IDs

Sensitive values have been removed or replaced with placeholders.

Always use your own credentials after importing the workflow.

## Project Purpose

This project was created as part of my AI Automation learning and portfolio work using n8n, APIs, validation logic, error handling, and Telegram automation.

## Future Improvements

Possible future upgrades include:

- Rain alerts
- Heavy rain warnings
- Heat / high-temperature alerts
- Humidity information
- Wind-speed alerts
- Smart weather recommendations
- Advanced weather notification rules