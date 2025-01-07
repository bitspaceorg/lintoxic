<div align = "center">

<h1> Lintoxic </h1>
<h2> Linting Toxicity</h2>
<h3> Kynnovate 2025 </h3>

</div>
Lintoxic (Linter for toxic content and beyond) is a pluggable, cost-effective, privacy-friendly, multilingual content moderation system. The project was born out of a need for open source moderation systems that would help organizations to effectively monitor and process content to filter out harmful or offensive content while staying in compliance with regulatory requirements for data.

It supports mixed-code detection and supports vernacular languages such as Tamil with mixed-code (Tanglish) for improved accuracy in detection of harmful content in local community services such as KYNHood, Koo, etc. providing a more inclusive and safe space for online interaction.

It supports processing of several file types such as audio, video, image and text for automated detection and flagging of potentially offensive or unacceptable content that goes against general community guidelines of a platform or service and supports NSFW content detection, false information detection, toxicity evaluation, etc.

## **Table of Contents**

- [Working](#working)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Proposal](#proposal)
- [Team Members](#team-members)
- [Contributing](#contributing)
  - [Development](#development)
- [Acknowledgements](#acknowledgements)
- [License](#license)

# Working

Lintoxic is a robust system that suppors features like fact checking, Profanity, Toxicity for english and mixed-code native languages such as Tanglish tailored specifically for Kynhood. The moderation system supports multi platform checking including images, text, audio and video formats. We also have lingual support for a few more native languages including French, German, Portuguese, Russian and much more !

## Image Moderation

1. **Content Upload** : The Image to be checked is added onto the Lintoxic dashboard to be checked if it is NSFW.
2. **Checking** : The image is then checked using the NSFW flagging model to filter out Images which do not follow platform guidelines.
3. **Reporting and Logging** : If the image is not safe and is logged and reported back to the user. Safe images are not logged or stored anywhere to protect the platform's data privacy.

## Audio Moderation

1. **Audio Upload** : The Audio to be checked is added on to the Lintoxic dashboard to check false information, vulgarity and profanity.
2. **Checking** : The Audio passes through the model and is checked for the NSFW guidelines and platform guidelines.
3. **Reporting and Logging** : The model report the cause of reporting and a and acceptedly detailed reason behind flagging an audio file and loggs it.

## Text Moderation

1. **Text Upload** : The text content is added onto the text box which support multi lingual and mixed code native languages.
2. **Checking** : The text then passes through various models (Hate-speech-CNERG/deoffxlmr-mono-tamil),(Detoxify - XLM-RoBERTa),(Detecting AI) for comprehensive flagging.
3. **Reporting and Logging** : Unnaceptable and misinformation spreading is reported and logged.

## Video Moderation

1. **Video Upload** : The video content is added to the dashboard.
2. **Checking** : The video is extracted in image frames and NSFW content is checked both in the image and audio component. This is an integration of audio and image moderation.
3. **Reporting and Logging** : If the video content is flagged as Not Safe For Work the videographic content is reported and logged.

# Features

1. **Multilingual Support**: Detects and flags harmful content in multiple languages, focusing on mixed-code languages such as Tanglish for local community services.
2. **Pluggable Architecture**: Easily integrates with existing systems and platforms for seamless content moderation.
3. **Content Type Compatibility**: Processes audio, video, images, and text to detect toxic, offensive, or unacceptable content.
4. **Automated Detection and Flagging**: Leverages existing models for automated flagging, reducing manual intervention and ensuring compliance with community guidelines.
5. **Enhanced Logging & Monitoring**: Provides detailed logs of flagged content for tracking and auditing moderation activities.
6. **Privacy-Focused**: Automatically deletes non-flagged content, ensuring compliance with data protection policies and reducing storage requirements.
7. **NSFW Flagging**: Detects and flags NSFW images, explicit audio, and harmful text embedded in images to maintain platform integrity.
8. **Video Processing**: Analyzes video content for inappropriate or harmful material, complementing image and audio moderation.

---

# Technologies Used

## Backend:

- **FastAPI**: Implementation of RESTful API meant to be integrated with content processing systems in
- **HuggingFace Transformers**: Leveraged by lintoxic for evaluation of NSFW content in images and video frames, harmful content in textual content or multimedia content by means of OCR for images and videos and ASR for audio and video. The models used by Lintoxic are:
  a. **Hate-speech-CNERG/deoffxlmr-mono-tamil**: Tanglish detection (mixed code)
  b. **Falconsai/nsfw_image_detection** - NSFW image detection
  c. **facebook/mbart-large-50-many-to-one-mmt** - Many to one translation for offensive content detection in audio
  d. **Detoxify - XLM-RoBERTa** (multilingual) for multilingual toxicity detection
- **Tesseract**: Used for performing OCR to retrieve textual content from both images and videos (by using OpenCV for frame extraction)
- **SpeechRecognition**: Used for translation of text in other languages to English for offensive content detection and transcriptions using Google Translate API
- **Detecting AI**: Used for factual accuracy checking while eliminating fact checking for ambiguous content as in conversations or comments
- **Logging**: For thread safe logging of offensive content and maintenance of moderation and production logs

Frontend of Lintoxic is developed using Streamlit to provide a versatile experience to evaluate performance of the moderation system for several file type and/or content which can be deployed seamlessly to the cloud using Streamlit Public cloud or other cloud service providers

///////////pls change the streamlit dashboard content given above ///////////////////

# Proposal

# Contributing

Contributions are welcome! Let us join hands to make Lintoxic a much more comprehensive and impactful project.

## Roadmap

- **Real-Time Content Moderation**: Implement real-time processing for live streams and chats.
- **Model Customization**: Support for user-provided models to enhance detection accuracy.
- **Dashboard**: Add a web-based dashboard for moderation insights and analytics.

## Development

Both Docker based builds and manual development mode are supported, and usage of Docker for containerization of the backend is still

### Prerequisites

You need to make sure that the following dependencies are available on your system for development:

### Backend

1. Python 3.12 or later
2. Poetry for dependency management
3. Tesseract OCR

### Steps to Run Locally

Access the Streamlit dashboard to perform moderation tasks. The dashboard provides an intuitive interface for analyzing text, images, and videos for toxic content. Launch the dashboard by following the instructions in the [Development](#development) section and navigate to [http://localhost:8501](http://localhost:8501).

### Prerequisites

Make sure that the following dependencies are available on your system for development:

1. Python: Version 3.12 or later (needed for lingua language detector to work properly)
2. Poetry: For dependency management
3. Tesseract OCR: Required for text detection in images

### Installing dependencies

Clone the Github repository for setting up the project and installing the needed dependencies:

git clone https://github.com/grittypuffy/lintoxic
cd lintoxic
poetry install

### Activate the virtual environment on Linux distributions. Use Scripts\Activate.ps1 in Windows for the same

```
source $(poetry env info --path)/bin/activate
Start the Streamlit dashboard with the following command:

poetry run python -m streamlit run lintoxic/app.py
```

You can now view your Streamlit app in your browser at [http://localhost:8501](http://localhost:8501).

/////////// pls change the Installing dependency as per your changes yesterday pls /////////////

# Acknowledgements

Lintoxic's developed during KYNNOVATE 2025 by Team Phoenix

## Team members

1. **Team Leader:** [Srivatsav Auswin](https://github.com/Sak1012)
2. [Keerthana R](https://github.com/grittypuffy)
3. [Immanuel Alex M](https://github.com/Alex03Immanuel)

# License

Lintoxic is licensed under MIT license, thus allowing permissive usage for your needs.
