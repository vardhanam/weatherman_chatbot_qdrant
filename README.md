# Weatherman Chatbot

This project implements a weatherman chatbot that provides weather information based on user queries. The chatbot uses natural language processing and machine learning techniques to understand user inputs and retrieve relevant weather data from a vector database.

## Features

- Retrieves weather data from the OpenMeteo API based on user-specified location
- Formats and preprocesses the weather data for efficient storage and retrieval
- Stores the weather data in a Qdrant vector database for fast similarity search
- Uses the Mistral-7B language model to understand user queries and generate responses
- Provides a user-friendly Gradio interface for interacting with the chatbot

## Prerequisites

- Python 3.7+
- Qdrant server running on `localhost` at port `6333`

## Installation

1. Clone the repository:

```bash
git clone https://github.com/vardhanam/weatherman_chatbot_qdrant.git
cd weatherman_chatbot_qdrant
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. Start the Qdrant server on `localhost` at port `6333`.

2. Access the chatbot interface by running all the cells one by one. The final `demo.launch` cell will spin up the bot.

3. Enter the location for which you want to retrieve weather data (e.g., "Eiffel Tower, Delhi") in the designated textbox and submit.

4. The chatbot will fetch and store the weather data for the specified location in the Qdrant vector database.

6. Interact with the chatbot by entering your queries in the chat interface. The chatbot will provide relevant weather information based on the stored data.

7. To clear the chat history, click the "Clear" button.

## Code Structure

- `weather_api(lat, long)`: Retrieves weather data from the OpenMeteo API based on latitude and longitude coordinates.
- `format_weather_data(weather_data)`: Formats the retrieved weather data into a readable format.
- `get_text_chunks_langchain(text)`: Splits the formatted weather data into chunks using the LangChain library.
- `get_lat_lon(location_name)`: Retrieves the latitude and longitude coordinates for a given location using the OpenStreetMap Nominatim API.
- `load_llm()`: Loads the Mistral-7B language model for text generation.
- `add_to_vectorstore(location)`: Adds the weather data for a specified location to the Qdrant vector database.
- `answer_query(message, chat_history)`: Processes user queries, retrieves relevant weather data from the vector database, and generates responses using the language model.

## Dependencies

- `requests`: For making HTTP requests to APIs.
- `gradio`: For building the user interface.
- `langchain`: For text processing and document splitting.
- `transformers`: For loading and using the language model.
- `qdrant_client`: For interacting with the Qdrant vector database.
- `langchain_community`: For embedding and vector store functionality.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

