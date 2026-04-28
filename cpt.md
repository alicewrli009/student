---
permalink: /CPT
---

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GPA Calculator</title>
  <link rel="stylesheet" href="https://pyscript.net/releases/2024.1.1/core.css" />
  <script type="module" src="https://pyscript.net/releases/2024.1.1/core.js"></script>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f5f3ef;
      color: #1a1a18;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 3rem 1rem 4rem;
    }

    .container { width: 100%; max-width: 680px; }

    h1 { font-size: 1.5rem; font-weight: 600; margin-bottom: 4px; }
    p.subtitle { font-size: 0.875rem; color: #7a7870; margin-bottom: 1.5rem; }

    .col-labels {
      display: grid;
      grid-template-columns: 1fr 80px 120px 36px;
      gap: 8px;
      margin-bottom: 6px;
      padding: 0 2px;
    }
    .col-labels span {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: #7a7870;
    }

    #courses-list { display: flex; flex-direction: column; gap: 8px; }

    .course-row {
      display: grid;
      grid-template-columns: 1fr 80px 120px 36px;
      gap: 8px;
      align-items: center;
    }

    input[type="text"], select {
      font-size: 14px;
      height: 38px;
      padding: 0 10px;
      border: 1px solid #dddad4;
      border-radius: 6px;
      background: #fff;
      color: #1a1a18;
      width: 100%;
      outline: none;
    }
    input[type="text"]:focus, select:focus { border-color: #2d5a3d; }

    .del-btn {
      height: 38px; width: 36px;
      border: 1px solid #dddad4;
      border-radius: 6px;
      background: #fff;
      color: #7a7870;
      cursor: pointer;
      font-size: 18px;
    }
    .del-btn:hover { background: #fdecea; color: #c0392b; }

    .add-btn {
      margin-top: 12px;
      height: 38px;
      padding: 0 16px;
      border: 1px dashed #dddad4;
      border-radius: 6px;
      background: transparent;
      color: #7a7870;
      font-size: 13px;
      cursor: pointer;
    }
    .add-btn:hover { border-color: #2d5a3d; color: #2d5a3d; background: #e8f0ea; }

    .divider { height: 1px; background: #dddad4; margin: 2rem 0; }

    .results-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-bottom: 12px;
    }

    .result-card {
      background: #fff;
      border: 1px solid #dddad4;
      border-radius: 10px;
      padding: 1.25rem;
      text-align: center;
    }
    .result-card.weighted { border-color: #2d5a3d; background: #e8f0ea; }

    .result-label {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: #7a7870;
      margin-bottom: 8px;
    }
    .result-card.weighted .result-label { color: #2d5a3d; }

    .result-value {
      font-family: monospace;
      font-size: 2.5rem;
      font-weight: 600;
    }
    .result-card.weighted .result-value { color: #2d5a3d; }

    .result-sub { font-size: 11px; color: #7a7870; margin-top: 6px; }

    .summary {
      background: #fff;
      border: 1px solid #dddad4;
      border-radius: 8px;
      padding: 0.75rem 1rem;
      font-size: 13px;
      color: #7a7870;
      display: none;
    }
  </style>
</head>
<body>
<div class="container">
  <h1>GPA Calculator</h1>
  <p class="subtitle">Enter your courses to calculate weighted and unweighted GPA</p>

  <div class="col-labels">
    <span>Course name</span>
    <span>Grade</span>
    <span>Course type</span>
    <span></span>
  </div>

  <div id="courses-list"></div>
  <button class="add-btn" id="add-btn">+ Add course</button>

  <div class="divider"></div>

  <div class="results-grid">
    <div class="result-card">
      <div class="result-label">Unweighted GPA</div>
      <div class="result-value" id="uw-gpa">—</div>
      <div class="result-sub">A=4 · B=3 · C=2 · D=1 · F=0</div>
    </div>
    <div class="result-card weighted">
      <div class="result-label">Weighted GPA</div>
      <div class="result-value" id="w-gpa">—</div>
      <div class="result-sub">AP/Honors A=5 · B=4 · C=3 · D=2 · F=1</div>
    </div>
  </div>

  <div class="summary" id="summary">
    <span id="summary-text"></span>
  </div>
</div>

<script type="py">
from pyscript import document, when

courses = []

UNWEIGHTED = {"A": 4, "B": 3, "C": 2, "D": 1, "F": 0}
WEIGHTED = {
    "Regular": {"A": 4, "B": 3, "C": 2, "D": 1, "F": 0},
    "Honors":  {"A": 5, "B": 4, "C": 3, "D": 2, "F": 1},
    "AP":      {"A": 5, "B": 4, "C": 3, "D": 2, "F": 1},
}


def calculate_gpa(course_list):
    if len(course_list) == 0:
        return 0.0, 0.0

    uw_total = 0
    w_total = 0

    for course in course_list:
        grade = course["grade"]
        course_type = course["type"]
        uw_total += UNWEIGHTED[grade]
        w_total += WEIGHTED[course_type][grade]

    unweighted_gpa = round(uw_total / len(course_list), 2)
    weighted_gpa = round(w_total / len(course_list), 2)

    return unweighted_gpa, weighted_gpa


def get_grade():
    valid_grades = ["A", "B", "C", "D", "F"]
    while True:
        grade = input("  Grade (A/B/C/D/F): ").strip().upper()
        if grade in valid_grades:
            return grade
        print("  Invalid grade. Please enter A, B, C, D, or F.")


def get_course_type():
    valid_types = {"1": "Regular", "2": "Honors", "3": "AP"}
    while True:
        print("  Course type:")
        print("    1 - Regular")
        print("    2 - Honors")
        print("    3 - AP")
        choice = input("  Enter 1, 2, or 3: ").strip()
        if choice in valid_types:
            return valid_types[choice]
        print("  Invalid choice. Please enter 1, 2, or 3.")


def display_results(course_list):
    if len(course_list) == 0:
        print("\nNo courses entered yet.")
        return

    print("\n--- Your Courses ---")
    for i, course in enumerate(course_list):
        name = course["name"] if course["name"] else f"Course {i + 1}"
        print(f"  {name}: {course['grade']} | {course['type']}")

    unweighted, weighted = calculate_gpa(course_list)

    print("\n--- GPA Results ---")
    print(f"  Unweighted GPA : {unweighted:.2f}  (A=4, B=3, C=2, D=1, F=0)")
    print(f"  Weighted GPA   : {weighted:.2f}  (AP/Honors A=5, B=4, C=3, D=2, F=1)")
    print(f"  Weighting boost: +{round(weighted - unweighted, 2):.2f}")


def main():
    print("=== GPA Calculator ===")
    print("Enter your courses one at a time. Type 'done' when finished.\n")

    while True:
        print("Options:")
        print("  1 - Add a course")
        print("  2 - View GPA")
        print("  3 - Clear all courses")
        print("  4 - Quit")
        choice = input("Choice: ").strip()

        if choice == "1":
            print("\nNew course:")
            name = input("  Course name (or press Enter to skip): ").strip()
            grade = get_grade()
            course_type = get_course_type()
            courses.append({"name": name, "grade": grade, "type": course_type})
            print(f"  Added: {name or 'Unnamed'} | {grade} | {course_type}\n")

        elif choice == "2":
            display_results(courses)
            print()

        elif choice == "3":
            courses.clear()
            print("All courses cleared.\n")

        elif choice == "4":
            display_results(courses)
            print("\nGoodbye!")
            break

        else:
            print("Invalid option. Please enter 1, 2, 3, or 4.\n")


main()
</script>
</body>
</html>