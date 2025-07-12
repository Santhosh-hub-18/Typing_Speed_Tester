# Typing_Speed_Testerimport time
import random

sentences = [
    "The quick brown fox jumps over the lazy dog.",
    "Typing speed matters in many professions.",
    "Practice daily to improve your typing skills.",
    "Python is a great language for beginners.",
    "Focus on accuracy before speed."
]

test_sentence = random.choice(sentences)

print("\n*** Typing Speed Tester ***")
print("Type the following sentence as fast and accurately as you can:\n")
print(">>>", test_sentence)
input("\nPress Enter when you're ready to start...")

start_time = time.time()
typed_sentence = input("\nStart Typing:\n>>> ")
end_time = time.time()

time_taken = end_time - start_time
time_taken_minutes = time_taken / 60
word_count = len(typed_sentence.split())
wpm = word_count / time_taken_minutes

correct_chars = 0
for i in range(min(len(test_sentence), len(typed_sentence))):
    if test_sentence[i] == typed_sentence[i]:
        correct_chars += 1

accuracy = (correct_chars / len(test_sentence)) * 100

print("\n--- Results ---")
print(f"Time Taken: {round(time_taken, 2)} seconds")
print(f"Typing Speed: {round(wpm, 2)} words per minute (WPM)")
print(f"Accuracy: {round(accuracy, 2)}%")
