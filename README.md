# Moby Dick Telegram Bot

This project implements a Telegram bot that uses a PDF knowledge base (Moby Dick) to answer user queries. Below is an overview of how the system works:

## Overview

- **Purpose**: To create an interactive Telegram bot that can answer questions based on the content of "Moby Dick" by Herman Melville.
- **Technologies Used**: Telegram Bot API, Make.com, JavaScript, GitHub Gist

## Workflow

1. **Receive Message from Telegram**
   - The bot is set up to receive messages through the Telegram Bot API using the "Watch Updates" module in Make.com.

2. **Text Source**
   - The full text of "Moby Dick" is hosted on GitHub Gist: [Moby Dick Text](https://gist.githubusercontent.com/Orestouio/402e6adb5aab42cb40a396f15edda9e2/raw/acbfc3c7f092d66ffb62414904909741658e628d/Mobby%2520Dick%2520text)
   - The bot downloads this text using an HTTP module in Make.com.

3. **Text Processing**
   - **Chunking**: The downloaded text is processed by a JavaScript module that chunks the book into manageable segments to be searched efficiently.
   - **Array Aggregator**: The chunks are then passed through an Array Aggregator in Make.com to handle the array of text segments.

4. **Query Processing**
   - Another JavaScript module parses these chunks to find the most relevant content to the user's query.

5. **API Integration**
   - The selected relevant chunk along with the user's query is then sent to an AI service for generating an answer.

6. **Send Response to Telegram**
   - The response from the AI service is formatted and sent back to the user via Telegram.

## Modules in Make.com:

- **Telegram Watch Updates**: Receives messages from users.
- **HTTP Download**: Fetches "Moby Dick" from GitHub Gist.
- **JavaScript (Chunking)**: Splits the book text into chunks.
- **Array Aggregator**: Aggregates chunked text for further processing.
- **JavaScript (Similarity Matching)**: Finds the chunk most similar to the user's query.
- **AI Service API Call**: Sends the query and context to an AI to get a response.
- **Telegram Send Message**: Sends the AI-generated answer back to the user.

## How to Use the Bot

- **Bot Username**: @App1MANbot
- **Usage**: Send any query related to "Moby Dick" to the bot via Telegram, and it will respond with an answer based on the book's content.

## Setup Instructions

1. **Create a Telegram Bot**:
   - Use BotFather to create a bot and obtain the API token.

2. **Make.com Integration**:
   - Sign up for Make.com if you haven't already.
   - Set up modules as described in the "Modules in Make.com" section above.

3. **GitHub Gist**:
   - The Moby Dick text is already hosted on GitHub Gist at the link provided in the Workflow section.

4. **API Configuration**:
   - If using an external AI service, configure the API call with your credentials.

5. **Test the Bot**:
   - Send messages to the bot to test various queries.

## Known Issues

- Message responses might be cut off if they exceed Telegram's message size limit. Consider implementing message splitting or alternative response methods.

## Future Enhancements

- Implement a more sophisticated similarity matching algorithm.
- Add functionality to handle follow-up questions within the same context.
- Allow users to upload their own text files for the bot to process.

## Contact

- **Author**: Orestis Theodorou
- **LinkedIn**: [Orestis Theodorou's LinkedIn](https://www.linkedin.com/in/orestis-theodorou-503b9b330/)
- **GitHub**: [Orestis Theodorou's GitHub](https://github.com/Orestouio)
