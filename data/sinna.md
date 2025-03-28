# Commands to set up the Zomi Language GitHub repository

# Initialize repository
git init
git branch -M main

# Create directory structure
mkdir -p data/raw data/processed data/audio data/dialects
mkdir -p src/translation src/frontend src/tools
mkdir -p docs/guidelines docs/resources
mkdir -p .github/workflows .github/ISSUE_TEMPLATE

# Create essential files
touch README.md
touch LICENSE
touch CONTRIBUTING.md
touch CODE_OF_CONDUCT.md
touch .gitignore

# Add initial README content
cat > README.md << 'EOF'
# Zomi Language Integration Project

Welcome to the **Zomi Language Integration Project**, an initiative aimed at facilitating the inclusion of the Zomi language in Google Translate and other language technology platforms.

## About Zomi

Zomi is a Sino-Tibetan language spoken by approximately 100,000+ people in regions of Myanmar and Northeast India. It belongs to the Kuki-Chin branch of Sino-Tibetan languages.

## Project Goals

1. **Google Translate Integration**: Advocate for Zomi's addition to Google Translate
2. **Interim Translation Tool**: Build a Zomi translation prototype
3. **Dataset Creation**: Develop comprehensive Zomi-English language resources
4. **Community Engagement**: Enable Zomi speakers to contribute

## Repository Structure

```
zomi-language/
├── data/           # Language datasets
│   ├── raw/        # Original collected data
│   ├── processed/  # Cleaned and processed data
│   ├── audio/      # Audio pronunciations
│   └── dialects/   # Dialect variations
├── src/            # Source code
│   ├── translation/  # Translation model code
│   ├── frontend/     # Web interface code
│   └── tools/        # Utility scripts
├── docs/           # Documentation
└── .github/        # GitHub templates and workflows
```

## Getting Started

[Installation and setup instructions will go here]

## How to Contribute

We welcome contributions from Zomi speakers, linguists, developers, and enthusiasts! See our [CONTRIBUTING.md](CONTRIBUTING.md) file for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
EOF

# Create .gitignore for Python projects
cat > .gitignore << 'EOF'
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# Distribution / packaging
dist/
build/
*.egg-info/

# Virtual environments
venv/
env/
ENV/

# IDE specific files
.idea/
.vscode/
*.swp
*.swo

# OS specific files
.DS_Store
Thumbs.db

# Project specific
*.model
data/processed/*.bin
data/raw/private/
EOF

# Create LICENSE file (MIT License)
cat > LICENSE << 'EOF'
MIT License

Copyright (c) 2025 Zomi Language Integration Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
EOF

# Create CONTRIBUTING.md
cat > CONTRIBUTING.md << 'EOF'
# Contributing to the Zomi Language Integration Project

Thank you for your interest in contributing to the Zomi Language Integration Project! This document provides guidelines for contributing to the repository.

## How Can You Contribute?

### 1. Language Data Contributions

- **Words and Translations**: Add Zomi words with English translations
- **Example Sentences**: Provide example sentences showing usage
- **Audio Recordings**: Submit audio pronunciations of Zomi words
- **Dialect Variations**: Document differences between Zomi dialects

### 2. Code Contributions

- **Translation Models**: Improve the machine translation capabilities
- **Web Interface**: Enhance the user interface for the translation tool
- **Utility Scripts**: Develop tools for data processing and analysis

### 3. Documentation

- **Language Resources**: Add documentation about Zomi grammar, phonetics, etc.
- **Tutorials**: Create guides for using the tools and resources
- **Translation Guides**: Develop guidelines for accurate translations

## Contribution Process

1. **Fork the Repository**: Create your own copy of the repository
2. **Create a Branch**: Make your changes in a new branch
3. **Submit a Pull Request**: Request that your changes be merged
4. **Code Review**: Your changes will be reviewed by maintainers
5. **Merge**: Approved changes will be merged into the main project

## Data Guidelines

- Ensure translations are accurate and natural
- Include regional variations when relevant
- Follow the established data format
- Cite sources for borrowed or adapted content

## Code Guidelines

- Write clean, commented code
- Include tests for new functionality
- Follow PEP 8 style guidelines for Python code
- Document API changes

## Questions?

If you have questions about contributing, please open an issue or contact the project maintainers.

Thank you for helping to preserve and promote the Zomi language!
EOF

# Create initial push
git add .
git commit -m "Initial repository setup"
# git remote add origin https://github.com/AMIDHRP/ZomiLanguage.git
# git push -u origin main


# Example structure for Zomi-English parallel data files

# Sample structure for train.tsv and test.tsv
"""
zomi_text\tenglish_text\tdialect\tdomain
Ka hong pai hi.\tI am coming.\ttedim\tconversation
Bangci na om hiam?\tHow are you?\ttedim\tconversation
Leitung tungah ki-itna om tahen.\tLet there be love on earth.\ttedim\treligious
Ni khat ni khat in.\tOne day at a time.\ttedim\tproverb
"""

# Sample structure for gatitos.tsv (vocabulary dataset)
"""
zomi_word\tenglish_word\tpart_of_speech\texample_zomi\texample_english\tdialect
inn\thouse\tnoun\tInn sung ka pai hi.\tI am entering the house.\ttedim
an\trice\tnoun\tAn ka ne hi.\tI am eating rice.\ttedim
pai\tgo\tverb\tInn ah ka pai hi.\tI am going home.\ttedim
hong\tcome\tverb\tHong pai in.\tCome here.\ttedim
"""

# Sample structure for dialects_examples.txt
"""
# Zomi Dialect Variations
## Common Greetings

| English | Tedim | Falam | Hakha | Mizo |
|---------|-------|-------|-------|------|
| Hello | Halou | Halou | Halou | Halo |
| How are you? | Bangci na om hiam? | Nangmah na dam maw? | Dah maw? | Engtin nge i awm? |
| Thank you | Lungdam ka ko hi | Lungdam kong ko | Ka lawm e | Ka lawm e |
| Goodbye | Kimu kik ding | Kan mu kik ding | Kan hmu ding | Kan hmu ang |

## Numbers 1-10

| English | Tedim | Falam | Hakha |
|---------|-------|-------|-------|
| One | Khat | Khat | Pakhat |
| Two | Nih | Nih | Pahnih |
| Three | Thum | Thum | Pathum |
| Four | Li | Li | Pali |
| Five | Nga | Nga | Panga |
| Six | Guk | Guk | Paruk |
| Seven | Sagih | Sari | Pasarih |
| Eight | Giat | Riat | Pariet |
| Nine | Kua | Kua | Pakua |
| Ten | Sawm | Sawm | Pahra |
"""

# Python script to create directory structure and sample files
import os

def create_data_structure():
    # Create directories if they don't exist
    directories = [
        'data/raw',
        'data/processed',
        'data/audio',
        'data/dialects'
    ]
    
    for directory in directories:
        os.makedirs(directory, exist_ok=True)
    
    # Create sample train.tsv
    train_sample = """zomi_text\tenglish_text\tdialect\tdomain
Ka hong pai hi.\tI am coming.\ttedim\tconversation
Bangci na om hiam?\tHow are you?\ttedim\tconversation
Leitung tungah ki-itna om tahen.\tLet there be love on earth.\ttedim\treligious
Ni khat ni khat in.\tOne day at a time.\ttedim\tproverb
Topa'n hong ompih hi.\tGod is with us.\ttedim\treligious
Nihkhat ciang hong pai in.\tCome tomorrow.\ttedim\tconversation
An ne khol ding.\tWe will eat rice together.\ttedim\tconversation
Lai ka sim hi.\tI am reading a book.\ttedim\teducation
Singkungte lei paikha hi.\tThe bird flew to the tree.\ttedim\tnature
Khuavak hong tang ta.\tThe day has dawned.\ttedim\tnature"""
    
    with open('data/raw/train.tsv', 'w') as f:
        f.write(train_sample)
    
    # Create sample gatitos.tsv
    gatitos_sample = """zomi_word\tenglish_word\tpart_of_speech\texample_zomi\texample_english\tdialect
inn\thouse\tnoun\tInn sung ka pai hi.\tI am entering the house.\ttedim
an\trice\tnoun\tAn ka ne hi.\tI am eating rice.\ttedim
pai\tgo\tverb\tInn ah ka pai hi.\tI am going home.\ttedim
hong\tcome\tverb\tHong pai in.\tCome here.\ttedim
topa\tgod\tnoun\tTopa' min phat in.\tPraise the Lord's name.\ttedim
lai\tbook\tnoun\tLai ka sim hi.\tI am reading a book.\ttedim
khua\tvillage\tnoun\tKa khua hoih hi.\tMy village is beautiful.\ttedim
tui\twater\tnoun\tTui ka dawn hi.\tI am drinking water.\ttedim
lim\tpicture\tnoun\tLim ka la hi.\tI am taking a picture.\ttedim
nu\tmother\tnoun\tKa nu inn ah om hi.\tMy mother is at home.\ttedim"""
    
    with open('data/raw/gatitos.tsv', 'w') as f:
        f.write(gatitos_sample)
    
    # Create sample dialects_examples.txt
    dialects_sample = """# Zomi Dialect Variations
## Common Greetings

| English | Tedim | Falam | Hakha | Mizo |
|---------|-------|-------|-------|------|
| Hello | Halou | Halou | Halou | Halo |
| How are you? | Bangci na om hiam? | Nangmah na dam maw? | Dah maw? | Engtin nge i awm? |
| Thank you | Lungdam ka ko hi | Lungdam kong ko | Ka lawm e | Ka lawm e |
| Goodbye | Kimu kik ding | Kan mu kik ding | Kan hmu ding | Kan hmu ang |

## Numbers 1-10

| English | Tedim | Falam | Hakha |
|---------|-------|-------|-------|
| One | Khat | Khat | Pakhat |
| Two | Nih | Nih | Pahnih |
| Three | Thum | Thum | Pathum |
| Four | Li | Li | Pali |
| Five | Nga | Nga | Panga |
| Six | Guk | Guk | Paruk |
| Seven | Sagih | Sari | Pasarih |
| Eight | Giat | Riat | Pariet |
| Nine | Kua | Kua | Pakua |
| Ten | Sawm | Sawm | Pahra |"""
    
    with open('data/dialects/dialects_examples.txt', 'w') as f:
        f.write(dialects_sample)
    
    print("Data structure created successfully!")

if __name__ == "__main__":
    create_data_structure()
