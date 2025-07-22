# CORSA - Course Data Analysis & Processing

CORSA is a Python-based data analysis tool designed for processing and analyzing university course information. The project focuses on scraping, cleaning, and analyzing course data from various sources, with specific support for AUA (American University of Armenia) course catalogs and general education requirements.

## Features

- **Course Data Scraping**: Extract course information from HTML sources and web APIs
- **Data Processing**: Clean and structure course data using pandas for analysis
- **AI Integration**: Leverage OpenAI API for intelligent data processing and analysis
- **Multiple Data Sources**: Support for different course data formats (Jenzabar, GenEds, AUA)
- **Jupyter Notebook Analysis**: Interactive data exploration and visualization

## Project Structure

```text
├── 1. Corsa_Jenza_F2025.ipynb      # Jenzabar course data processing
├── 2. Corsa_Geneds_F2025.ipynb     # General education courses analysis
├── 3. Corsa_AUA_Merged_F2025.ipynb # Combined AUA course data analysis
├── pyproject.toml                   # Project dependencies and configuration
├── .env.example                     # Environment variables template
├── .gitignore                       # Git ignore rules
└── README.md                        # This file
```

## Requirements

- Python 3.11+
- Dependencies managed via `uv` (see `pyproject.toml`)

### Core Dependencies

- `beautifulsoup4` - HTML parsing and web scraping
- `pandas` - Data manipulation and analysis
- `requests` - HTTP requests for data fetching
- `openai` - OpenAI API integration
- `python-dotenv` - Environment variable management
- `ipykernel` - Jupyter notebook support

## Installation

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd corsa
   ```

2. **Install dependencies using uv:**

   ```bash
   source ./.venv/bin/activate && uv sync
   ```

3. **Set up environment variables:**

   ```bash
   cp .env.example .env
   # Edit .env and add your OpenAI API key
   ```

## Configuration

Create a `.env` file in the project root with the following variables:

```bash
OPENAI_API_KEY=your_openai_api_key_here
```

## Usage

### Running Jupyter Notebooks

The project consists of three main analysis notebooks:

1. **Jenzabar Course Processing** (`1. Coursa_Jenza_F2025.ipynb`)
   - Processes course data from Jenzabar HTML files
   - Extracts course information, schedules, and metadata
   - Uses OpenAI for intelligent data enhancement

   > Note: Before running this notebook, you must visit AUA SONIS Jenzabar, make sure
   > that all courses are selected and visible for you using the course limit selector,
   > and save the HTML contents of that page to a folder in this project called `.localdata`.
   > The filename must be `raw__jenzabar.html`.

2. **General Education Analysis** (`2. Coursa_Geneds_F2025.ipynb`)
   - Fetches and processes general education course requirements from AUA's official website
   - Web scraping of course catalog data
   - Data cleaning and structure standardization

3. **AUA Merged Analysis** (`3. Coursa_AUA_Merged_F2025.ipynb`)
   - Combines data from multiple sources
   - Comprehensive analysis of AUA course offerings
   - Cross-references course data across different systems

### Running the Notebooks

You can run the notebooks through your preferred IDE or the command line. I used Jupyter Lab
extension for VS Code for running.

## Data Sources

The project processes course data from multiple sources:

- **AUA SONIS Jenzabar System**: HTML-based course catalog data
- **AUA General Education Website**: Web-based course requirement data

All source data files are stored in `.localdata/` directory (excluded from version control).

## Output

The analysis generates:

- Cleaned CSV files with structured course data
- Data visualizations and summary statistics
- AI-enhanced course descriptions and metadata
- Cross-referenced course information across systems

> The final generated outuput is going to be named `aua__all-courses-merged.csv`.

## Development

### Architecture

- **Notebooks**: Interactive analysis and data processing workflows
- **Data**: Raw and processed course data (in `.localdata/`)
- **Configuration**: Environment-based settings and API keys

### Adding New Data Sources

1. Create a new Jupyter notebook following the naming convention
2. Implement data extraction and cleaning logic
3. Standardize output format to match existing schemas
4. Update this README with new data source information

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For questions, issues, or contributions, please:

1. Check existing [Issues](../../issues) for similar problems
2. Create a new issue with detailed information
3. Include relevant notebook outputs and error messages

---

**Note**: This project handles educational data. Please ensure compliance with institutional data policies and privacy requirements when using or contributing to this project. This project is not endorsed, sponsored, or affiliated with the American University of Armenia.
