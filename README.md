# OpenUrantia - Open-Source Urantia Papers Data

Welcome to the "Open-Source Urantia Papers Data" repository, a hub for innovation and development of diverse applications leveraging the rich and profound content of the Urantia Papers. This open-source collection provides both the Urantia Papers content in a structured JSON format and MP3 audio files for each paper and node. It is designed to facilitate easy integration and accessibility of the Urantia Papers content for various projects, from academic research tools to spiritual study apps. Please use this data freely in your personal and commercial projects, and feel free to contribute to its enhancement and expansion.

## JSON Content Structure

The repository contains the Urantia Papers and their parts in JSON format, structured as follows:

- **Papers**: Each paper is represented as a separate JSON file, named from `000.json` to `196.json`.
- **Parts**: The parts are represented as JSON files named from `1-part.json` to `4-part.json`.
- **Combined Index**: A combined JSON file named `index.json` includes all papers for easy access and querying.

### JSON Structure

#### Papers

Each paper JSON file follows this structure:

```json
{
  "globalId": "string",
  "htmlText": "string",
  "labels": ["string"],
  "language": "string",
  "objectID": "string",
  "paperId": "string",
  "paperSectionId": "string",
  "paperSectionParagraphId": "string",
  "paperTitle": "string",
  "paragraphId": "string",
  "partId": "string",
  "sectionId": "string",
  "sectionTitle": "string",
  "sortId": "string",
  "standardReferenceId": "string",
  "text": "string",
  "type": "string",
  "typeRank": "number"
}
```

#### Parts

Each part JSON file follows this structure:

```json
{
  "globalId": "string",
  "htmlText": "string",
  "labels": ["string"],
  "language": "string",
  "objectID": "string",
  "partId": "string",
  "partTitle": "string",
  "partSponsorship": "string",
  "sortId": "string",
  "type": "string",
  "typeRank": "number"
}
```

## MP3 Audio Content

The repository includes the Urantia Papers audiobook content in MP3 format, organized both by paper and by node. The audio files provide an alternative way to experience the teachings and narratives of the Urantia Papers. The audio was generated using advanced text-to-speech technology utilizing OpenAI's tts-1-hd model with the "Nora" voice.

### Audio Structure

#### Papers

- **Location:** `/data/mp3/eng/papers/`
- **Filename Format:** `{paper_id}.mp3` (e.g., `000.mp3`, `001.mp3`, ..., `196.mp3`)
- **CDN URL:** `https://cdn.openurantia.com/{paper_id}.mp3`
  - Example: [https://cdn.openurantia.com/43.mp3](https://cdn.openurantia.com/43.mp3) (Paper 43)

#### Nodes

- **Location:** `/data/mp3/eng/tts-1-hd-nova/`
- **Filename Format:** `tts-1-hd-nova-{part_number}:{paper_number}.{section_number}.{paragraph_number}.mp3`
- **CDN URL:** `https://cdn.openurantia.com/tts-1-hd-nova-{part_number}:{paper_number}.{section_number}.{paragraph_number}.mp3`
  - Example: [https://cdn.openurantia.com/tts-1-hd-nova-2:43.1.7.mp3](https://cdn.openurantia.com/tts-1-hd-nova-2:43.1.7.mp3) (Part 2: Paper 43 . Section 1 . Paragraph 7)

### CDN Access

The audio files can also be accessed via our CDN at [https://cdn.openurantia.com/](https://cdn.openurantia.com/). The CDN provides faster and more reliable access to the content.

## Repo Size Warning

Please note that this repository contains a **LARGE** amount of data, including JSON files for each paper and part of the Urantia Papers, as well as MP3 audio files for each paper and even each paragraph. **The total size of the repository is substantial due to the volume of content.** If you are only interested in the JSON data, you can clone the repository without downloading the audio files by using the following command:

### Cloning Without Audio Files

To clone the repository without the audio files, use Git's sparse-checkout feature as follows:

1. **Clone the Repository:**
   Start by cloning the repository but don't check out files immediately.

   ```sh
   git clone --no-checkout https://github.com/Open-Urantia/OpenUrantia-data.git
   cd OpenUrantia-data
   ```

2. **Enable Sparse-Checkout:**
   Enable the sparse-checkout feature for your local repository.

   ```sh
   git sparse-checkout init --cone
   ```

3. **Exclude the `data/mp3` Directory:**
   Configure sparse-checkout to exclude the `data/mp3` directory.

   ```sh
   echo "!data/mp3/*" >> .git/info/sparse-checkout
   ```

4. **Check Out the Files:**
   Now, update your working directory to reflect the sparse-checkout configuration.

   ```sh
   git checkout main
   ```

By following these steps, you can clone the repository without downloading the large MP3 audio files, focusing only on the JSON data, which avoids downloading GBs of audio content.

## Usage

This data is provided under the MIT license, allowing for free use in both personal and commercial projects. The structured JSON format and MP3 audio files of the Urantia Papers content are ideal for a wide range of applications, from academic research tools to spiritual study apps.

### Leveraging Search Services like Algolia

The JSON structure of the Urantia Papers content is particularly suited for integration with search services such as [Algolia](https://www.algolia.com/), which can provide fast and powerful search capabilities. This can significantly enhance the accessibility and user experience of applications that utilize the Urantia Papers content.

To integrate this data with Algolia or similar services, consider the following general steps:

1. **Format the Data:** Ensure the JSON data is in a format compatible with your search service's requirements. This might involve structuring the data with specific fields that you want to be searchable or highlighted in search results.
2. **Upload the Data:** Use the provided APIs or tools from the search service to upload your JSON data. For Algolia, this typically involves using their API clients available in various programming languages to push data to an index.
3. **Configure the Index:** Customize the search settings according to your needs. This could include setting up custom ranking, searchable attributes, and filters to refine the search experience.
4. **Integrate Search into Your Application:** Utilize the search service's API to query the index and retrieve results. This can be done through direct API calls or using client libraries provided by the service.
5. **Optimize and Update:** Regularly update the data in your search index to reflect any changes or additions to the Urantia Papers content. Also, monitor and tweak the search performance and relevance based on user feedback and analytics.

By following these steps, developers can create sophisticated search experiences that allow users to quickly and efficiently find the information they need within the Urantia Papers content.

(Need some help using this data? [Reach out to us on our Issues page](https://github.com/Open-Urantia/urantia-papers-json/issues) and we'll be happy to assist you!)

### Example Applications

- **Educational Platforms:** Incorporate the Urantia Papers content into study courses or educational materials, with powerful search tools to explore complex topics.
- **Spiritual Study Apps:** Develop applications that allow users to study the Urantia Papers, bookmark sections, and search for concepts or teachings.
- **Research Tools:** Create tools that aid in academic or personal research, enabling users to query the Urantia Papers for specific themes, words, or phrases.

This data's flexibility and openness encourage innovation and the development of diverse applications that can benefit from the rich and profound content of the Urantia Papers.

## Roadmap

Future enhancements for this repository include:

- Providing translations for each paper in multiple languages.
- Extending the dataset with additional metadata and resources related to the Urantia Papers, such as AI-generated summaries or keyword extraction.

## Contributing

Contributions are welcome! Whether it's adding new features, improving documentation, or reporting issues, your input is valuable. Please refer to the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on how to contribute.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
