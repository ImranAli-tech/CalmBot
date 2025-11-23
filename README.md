CalmBot – Meditation Guide 🧘‍♂️🤖

A Python-based interactive meditation assistant that guides users through relaxing breathing exercises using voice instructions, calming music, and humorous responses. CalmBot helps users stay focused, relaxed, and entertained during meditation.

🌿 Overview

CalmBot is a meditation guide that uses text-to-speech, background music, and dynamic humor to make meditation more engaging. The bot walks users through breathing cycles and reacts based on a “patience level,” making each session unique and fun.

✨ Features

🗣 Voice-guided meditation using pyttsx3

🎵 Relaxing background music played through threading

😄 Funny & sarcastic responses based on user “patience level”

🧘 Guided breathing cycles with timed instructions

📜 Certificate of Calmness summary at the end

💻 Fully terminal-based, lightweight, and beginner-friendly

📂 Project Structure CalmBot/ │── meditation.py # Main project file │── music/ # Folder for meditation audio tracks │ ├── please-calm-my-mind.mp3 │ ├── meditation-music.mp3 │ └── eternal-drift.mp3 └── README.md

🛠 Libraries Used

pyttsx3 – Text-to-speech engine

time – Timing and breathing intervals

random – Randomized humor and track selection

playsound – Audio playback

threading – Background music without blocking execution

🚀 How to Run

Install Required Libraries pip install pyttsx3 playsound

Place your music files

Add .mp3 files to the project folder (or update the paths in the code).

Run the Program python meditation.py
🧘 How It Works

CalmBot welcomes you with a soothing voice.

Background meditation music begins playing.

You go through breathing cycles:

Breathe in

Hold

Breathe out

CalmBot randomly generates funny comments.

Your “patience level” changes dynamically.

You receive your Certificate of Calmness at the end. 🎯 Purpose of the Project

This project was developed as part of Python Lab (5.0CE252E02) under the CSE Department, MRIIRS. It demonstrates:

Voice synthesis

Threading

Interactive console design

Fun & creative programming
