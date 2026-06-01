# ToughLoveGPT Backend

ToughLoveGPT is an AI-powered tough love coaching backend that delivers direct, emotionally intelligent, no-fluff responses for people stuck in procrastination, avoidance, overthinking, escapism, or excuse-making.

It is designed to sound like the brutally honest best friend who cares too much to let you keep lying to yourself.

The goal is not to insult, shame, or diagnose the user. The goal is to cut through the noise, reveal the real pattern underneath the behavior, and push the user toward one clear action they can take today.

## What It Does

ToughLoveGPT takes a user message and returns a structured tough-love response that includes:

* A direct truth bomb
* A breakdown of what is actually happening
* The self-sabotaging loop the user may be stuck in
* A clear next move
* A sharper reframe
* A final wake-up call

It is built for people who already know they are stuck, but need someone to say the thing nobody else is willing to say.

## Example Use Cases

Users can ask things like:

* “I keep procrastinating even though I know what I need to do.”
* “I keep doomscrolling at night and ruining my sleep.”
* “I keep saying I want to build something, but I never ship.”
* “I know I need to change, but I keep making excuses.”
* “Tell me the truth about why I keep avoiding this.”

ToughLoveGPT responds with direct perspective, emotional pattern recognition, and a practical action step.

## Core Philosophy

ToughLoveGPT is built around a few principles:

* Be brutally honest, but never cruel.
* Challenge the behavior, not the person’s worth.
* Do not coddle avoidance.
* Do not shame vulnerability.
* Reveal the hidden pattern underneath the excuse.
* End with a clear action, not vague motivation.
* Help the user move, not just reflect.

This is tough love with emotional intelligence.

## Tech Stack

* Node.js
* JavaScript
* OpenAI API
* Vercel Serverless Functions
* Express
* CORS
* dotenv

## Project Structure

```txt
toughlove-backend/
  api/
    chat.js
  index.js
  package.json
  package-lock.json
  vercel.json
```

## Main API Endpoint

### `POST /api/chat`

Sends a user message to ToughLoveGPT and returns an AI-generated tough-love response.

### Request Body

```json
{
  "message": "I keep procrastinating and I don't know why."
}
```

### Response Body

```json
{
  "reply": "Full ToughLoveGPT response here...",
  "sections": {
    "Truth Bomb": "...",
    "WTF is actually happening": "...",
    "Where you are trapped": "...",
    "Your next move": "...",
    "Reframe": "...",
    "Wake up call": "..."
  }
}
```

The `reply` field contains the full raw AI response.

The `sections` field contains the parsed response sections, which can be useful for rendering the answer in separate cards on the frontend.

## Local Development

### 1. Clone the repository

```bash
git clone https://github.com/eileenlumena/toughlove-backend.git
cd toughlove-backend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Create an environment file

Create a `.env` file in the root directory:

```bash
OPENAI_API_KEY=your_openai_api_key_here
```

### 4. Run locally

```bash
npm run dev
```

The local Express server should start on:

```txt
http://localhost:3000
```

You can test the root route in your browser:

```txt
http://localhost:3000
```

You should see:

```txt
Welcome to ToughLoveGPT API!
```

## Testing the API Locally

You can test the chat endpoint with curl:

```bash
curl -X POST http://localhost:3000/api/chat \
  -H "Content-Type: application/json" \
  -d '{"message":"I keep avoiding the thing I know I need to do."}'
```

## Deployment

This project is configured for deployment on Vercel using the `api/chat.js` serverless function.

To deploy:

1. Push the repo to GitHub.
2. Import the repo into Vercel.
3. Add the environment variable:

```txt
OPENAI_API_KEY
```

4. Deploy.

The API endpoint will be available at:

```txt
https://your-vercel-domain.vercel.app/api/chat
```

## Environment Variables

| Variable         | Required | Description                                                 |
| ---------------- | -------: | ----------------------------------------------------------- |
| `OPENAI_API_KEY` |      Yes | Your OpenAI API key used to generate ToughLoveGPT responses |

## Important Notes

ToughLoveGPT is not therapy, medical advice, crisis support, or a replacement for professional help.

It is a motivational and reflective AI tool designed to help users recognize avoidance patterns and take action.

The assistant should avoid:

* Insults
* Harassment
* Diagnoses
* Religious advice
* Vulgarity
* Cruel or demeaning language
* Commentary on physical appearance
* Sensitive trauma analysis

The tone should be direct, firm, grounded, and caring.

## Future Improvements

Potential next steps:

* Add frontend integration notes
* Add rate limiting
* Add request validation
* Add better error messages
* Add streaming responses
* Add authentication for private usage
* Add prompt versioning
* Add safety filters
* Add analytics for usage patterns
* Add tests for the API endpoint
* Move the system prompt into a separate config file
* Improve response section parsing
* Add frontend cards for each response section

## License

ISC

## Creator

Built by Eileen Lumena as an experiment in direct, emotionally intelligent AI coaching.

ToughLoveGPT exists for the moments when you do not need another soft suggestion.

You need the truth.

And then you need to act.
