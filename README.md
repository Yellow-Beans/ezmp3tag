# EzMP3Tag

# Music Metadata Retrieval

This Python script retrieves and resolves music metadata from various sources, including Spotify, Deezer, Discogs, and MusicBrainz, using fuzzy matching for improved accuracy. It integrates environmental variable management and error handling for robust operation.

## Features

- **Metadata Sources**: Fetches data from multiple APIs:
  - Spotify
  - Deezer
  - Discogs
  - MusicBrainz
  - Last.fm (for tags)

- **Fuzzy Matching**: Uses `fuzzywuzzy` for string similarity, ensuring the best match for artist and track names.

- **Year Parsing**: Handles various date formats to extract the release year accurately.

- **Conflict Resolution**: Combines metadata from different sources, preferring the best available data based on predefined priorities.

## Requirements

- Python 3.x
- `dotenv`: For loading environment variables.
- `fuzzywuzzy`: For fuzzy string matching.
- `requests`: For making HTTP requests to the APIs.
- `musicbrainzngs`: For interfacing with the MusicBrainz API.
- `oauth2`: For handling OAuth 2.0 authentication.
- `spotipy`: For accessing the Spotify Web API.

You can install the required packages using pip:

```
pip install python-dotenv fuzzywuzzy requests musicbrainzngs oauth2 spotipy
```

## Setup
1. Clone the Repository: Clone or download this repository to your local machine.

2. Create a `.env` File: Store your API keys and credentials in a `.env` file. Example format:


```
SPOTIFY_API_KEY=your_spotify_api_key
DEEZER_API_KEY=your_deezer_api_key
DISCOGS_API_KEY=your_discogs_api_key
LASTFM_API_KEY=your_lastfm_api_key
Run the Script: Execute the script to retrieve metadata for a specific track.
```
3. Run the Script: Execute the script to retrieve metadata for a specific track.

```py  
python your_script_name.py
```
## Usage
The main function to retrieve music metadata is `get_music_metadata(track: str)`. It accepts a track name as input and returns a dictionary containing the resolved metadata.

## Example

```py
if __name__ == "__main__":
    track_name = "Bohemian Rhapsody"
    metadata = get_music_metadata(track_name)
    print("AI-Resolved Metadata:", metadata)
```
## Functions Overview
- `best_match(source_value, candidate_values):` Returns the best match from candidate values based on similarity to the source value.

- `parse_year(year_string):` Parses a year from a string format, returning None for invalid formats.

- `ai_resolve_metadata(mb_metadata, spotify_metadata, deezer_metadata, discogs_metadata, lastfm_tags):` Combines metadata from different sources using AI logic to determine the best values.

- `get_music_metadata(track):` Fetches metadata from all sources and combines the results.

## Contributing
Contributions are welcome! If you find bugs or have suggestions, feel free to create an issue or submit a pull request.

## License
This project is licensed under the MIT License - see the [LICENSE](https://opensource.org/licenses/MIT)
 file for details.