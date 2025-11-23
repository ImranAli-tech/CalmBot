import pyttsx3
import time
import random
from playsound import playsound
import threading

# Initialize text-to-speech engine
engine = pyttsx3.init()

def speak(text):
    """Convert text to speech and print it."""
    print(f"CalmBot 😌: {text}")
    engine.say(text)
    engine.runAndWait()

def get_random_funny_line(patience_level):
    """Return a funny or sarcastic line depending on CalmBot’s patience."""
    funny_lines = {
        3: [
            "You're doing great. Inner peace is near. Probably.",
            "Ahh... the sound of calm... or was that your stomach?",
        ],
        2: [
            "You’re supposed to be breathing, not checking your phone 😤",
            "Focus! Even my circuits are calmer than you right now.",
        ],
        1: [
            "Okay seriously... are you meditating or buffering?",
            "You test my patience, human. I’m calm… I’m calm… maybe.",
        ],
        0: [
            "I give up. Namaste and goodbye. 😤💨",
            "I’m out of patience. Try yoga next time!",
        ],
    }
    return random.choice(funny_lines.get(patience_level, funny_lines[3]))

def play_random_music():
    """Play one of the meditation tracks randomly in the background."""
    music_files = [
        "please-calm-my-mind-125566.mp3",
        "meditation-music-427644.mp3",
        "eternal-drift-music-429062.mp3"
    ]
    chosen_track = random.choice(music_files)
    print(f"\n🎵 Playing background track: {chosen_track}\n")
    # Play in a separate thread so it doesn't block the meditation
    threading.Thread(target=playsound, args=(chosen_track,), daemon=True).start()

def meditate(cycles=3, patience_level=3):
    """Main meditation loop."""
    speak("Welcome to AI Meditation Guide — CalmBot.")
    speak("Let's begin your journey to calmness.")
    
    # Start random background music
    play_random_music()

    for i in range(cycles):
        speak(f"Cycle {i+1} begins.")
        
        speak("Breathe in... deeply.")
        time.sleep(3)

        speak("Hold it...")
        time.sleep(2)

        speak("Now breathe out slowly...")
        time.sleep(4)

        # Random chance for funny/sarcastic line
        if random.random() < 0.4:
            speak(get_random_funny_line(patience_level))

        # Randomly reduce patience
        if random.random() < 0.3:
            patience_level = max(0, patience_level - 1)

        time.sleep(2)

        if patience_level == 0:
            speak("Session ended early because I need a break too 😤")
            break

    session_summary(patience_level)

def session_summary(patience_level):
    """Print and speak a funny 'Certificate of Calmness'."""
    speak("Meditation complete!")
    print("\n🪷 ==== Certificate of Calmness ==== 🪷")
    if patience_level == 3:
        print("You remained calm and focused. Even CalmBot is impressed! 😇")
    elif patience_level == 2:
        print("Pretty good! A few distractions, but peace was achieved. 🌿")
    elif patience_level == 1:
        print("You barely made it... CalmBot almost screamed. 😤")
    else:
        print("You broke CalmBot’s patience. Try again tomorrow! 💀")
    print("=====================================")
    speak("Thank you for meditating with me. Stay calm, human.")

# Run only when executed directly
if __name__ == "__main__":
    try:
        meditate(cycles=3, patience_level=3)
    except KeyboardInterrupt:
        speak("Meditation interrupted! Even I felt that panic.")
        print("\nSession terminated by user.")
