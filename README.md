# quizz-application
# ==========================================
# Python Quiz Application
# ==========================================

def display_question(question_number, question_data):
    """Display a question and its options."""
    print("\n" + "=" * 50)
    print(f"Question {question_number}: {question_data['question']}")
    print("=" * 50)

    for option, text in question_data["options"].items():
        print(f"{option}. {text}")


def get_answer():
    """Get and validate the user's answer."""
    while True:
        answer = input("\nEnter your answer (A/B/C/D): ").strip().upper()

        if answer in ["A", "B", "C", "D"]:
            return answer

        print("Invalid choice! Please enter only A, B, C, or D.")


def run_quiz():
    """Run the complete quiz."""
    
    questions = [
        {
            "question": "Which keyword is used to define a function in Python?",
            "options": {
                "A": "function",
                "B": "def",
                "C": "func",
                "D": "define"
            },
            "answer": "B"
        },
        {
            "question": "Which data type is used to store True or False?",
            "options": {
                "A": "String",
                "B": "Integer",
                "C": "Boolean",
                "D": "Float"
            },
            "answer": "C"
        },
        {
            "question": "Which symbol is used for comments in Python?",
            "options": {
                "A": "//",
                "B": "/* */",
                "C": "<!-- -->",
                "D": "#"
            },
            "answer": "D"
        },
        {
            "question": "Which function is used to display output in Python?",
            "options": {
                "A": "print()",
                "B": "display()",
                "C": "output()",
                "D": "show()"
            },
            "answer": "A"
        },
        {
            "question": "Which of the following is a Python list?",
            "options": {
                "A": "{1, 2, 3}",
                "B": "(1, 2, 3)",
                "C": "[1, 2, 3]",
                "D": "<1, 2, 3>"
            },
            "answer": "C"
        },
        {
            "question": "Which operator is used for exponentiation in Python?",
            "options": {
                "A": "^",
                "B": "**",
                "C": "//",
                "D": "%%"
            },
            "answer": "B"
        },
        {
            "question": "Which function is used to find the length of a list?",
            "options": {
                "A": "size()",
                "B": "length()",
                "C": "count()",
                "D": "len()"
            },
            "answer": "D"
        },
        {
            "question": "Which loop is commonly used to iterate over a sequence?",
            "options": {
                "A": "for",
                "B": "repeat",
                "C": "loop",
                "D": "iterate"
            },
            "answer": "A"
        },
        {
            "question": "Which keyword is used to create a class in Python?",
            "options": {
                "A": "object",
                "B": "class",
                "C": "create",
                "D": "struct"
            },
            "answer": "B"
        },
        {
            "question": "Which extension is normally used for a Python file?",
            "options": {
                "A": ".java",
                "B": ".cpp",
                "C": ".py",
                "D": ".python"
            },
            "answer": "C"
        }
    ]

    score = 0
    total_questions = len(questions)

    print("\n" + "*" * 50)
    print("       WELCOME TO PYTHON QUIZ APPLICATION")
    print("*" * 50)

    name = input("\nEnter your name: ").strip()

    if name == "":
        name = "User"

    print(f"\nHello, {name}!")
    print(f"There are {total_questions} questions in this quiz.")
    print("Choose the correct option: A, B, C, or D.")

    input("\nPress Enter to start the quiz...")

    # Ask each question
    for question_number, question_data in enumerate(questions, start=1):

        display_question(question_number, question_data)

        user_answer = get_answer()
        correct_answer = question_data["answer"]

        if user_answer == correct_answer:
            print("Correct! ✓")
            score += 1
        else:
            print(
                f"Wrong! ✗ The correct answer is "
                f"{correct_answer}."
            )

    # Calculate result
    wrong_answers = total_questions - score
    percentage = (score / total_questions) * 100

    print("\n" + "=" * 50)
    print("              QUIZ RESULT")
    print("=" * 50)

    print(f"Name           : {name}")
    print(f"Total Questions: {total_questions}")
    print(f"Correct Answers: {score}")
    print(f"Wrong Answers  : {wrong_answers}")
    print(f"Score          : {score}/{total_questions}")
    print(f"Percentage     : {percentage:.2f}%")

    # Performance message
    if percentage >= 80:
        print("Performance    : Excellent!")
    elif percentage >= 60:
        print("Performance    : Good Job!")
    elif percentage >= 40:
        print("Performance    : Keep Practicing!")
    else:
        print("Performance    : Need More Practice!")

    print("=" * 50)


def main():
    """Main function of the application."""

    while True:
        run_quiz()

        print("\nDo you want to play again?")
        choice = input("Enter Y for Yes or N for No: ").strip().upper()

        if choice == "N":
            print("\nThank you for playing!")
            print("Have a great day!")
            break

        elif choice != "Y":
            print("\nInvalid choice. Quiz will end.")
            break


# Program starts here
if __name__ == "__main__":
    main()
