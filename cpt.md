---
permalink: /CPT
---


<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GPA Calculator</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://pyscript.net/releases/2024.1.1/core.css" />
  <script type="module" src="https://pyscript.net/releases/2024.1.1/core.js"></script>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #f5f3ef;
      --surface: #ffffff;
      --border: #dddad4;
      --text: #1a1a18;
      --muted: #7a7870;
      --accent: #2d5a3d;
      --accent-light: #e8f0ea;
      --danger: #c0392b;
      --mono: 'DM Mono', monospace;
      --sans: 'DM Sans', sans-serif;
    }

    body {
      font-family: var(--sans);
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 3rem 1rem 4rem;
    }

    .container { width: 100%; max-width: 680px; }

    header { margin-bottom: 2.5rem; }
    header h1 {
      font-family: var(--mono);
      font-size: 1.5rem;
      font-weight: 500;
      letter-spacing: -0.02em;
    }
    header p { font-size: 0.875rem; color: var(--muted); margin-top: 4px; }

    .col-labels {
      display: grid;
      grid-template-columns: 1fr 90px 130px 36px;
      gap: 8px;
      margin-bottom: 6px;
      padding: 0 2px;
    }
    .col-labels span {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: var(--muted);
    }

    #courses-list { display: flex; flex-direction: column; gap: 8px; }

    .course-row {
      display: grid;
      grid-template-columns: 1fr 90px 130px 36px;
      gap: 8px;
      align-items: center;
      animation: fadeIn 0.18s ease;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-6px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    input[type="text"], select {
      font-family: var(--sans);
      font-size: 14px;
      height: 38px;
      padding: 0 10px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background: var(--surface);
      color: var(--text);
      width: 100%;
      outline: none;
      transition: border-color 0.15s;
    }
    input[type="text"]:focus, select:focus { border-color: var(--accent); }

    .del-btn {
      height: 38px; width: 36px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background: var(--surface);
      color: var(--muted);
      cursor: pointer;
      font-size: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background 0.15s, color 0.15s;
    }
    .del-btn:hover { background: #fdecea; border-color: #e8b4b0; color: var(--danger); }

    .add-btn {
      margin-top: 12px;
      height: 38px;
      padding: 0 16px;
      border: 1px dashed var(--border);
      border-radius: 6px;
      background: transparent;
      color: var(--muted);
      font-family: var(--sans);
      font-size: 13px;
      cursor: pointer;
      transition: all 0.15s;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }
    .add-btn:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-light); }

    .divider { height: 1px; background: var(--border); margin: 2rem 0; }

    .results-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-bottom: 12px;
    }

    .result-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.25rem;
      text-align: center;
    }
    .result-card.weighted { border-color: var(--accent); background: var(--accent-light); }

    .result-label {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: var(--muted);
      margin-bottom: 8px;
    }
    .result-card.weighted .result-label { color: var(--accent); }

    .result-value {
      font-family: var(--mono);
      font-size: 2.5rem;
      font-weight: 500;
      color: var(--text);
      line-height: 1;
    }
    .result-card.weighted .result-value { color: var(--accent); }

    .result-sub { font-size: 11px; color: var(--muted); margin-top: 6px; }

    .summary {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 0.75rem 1rem;
      font-size: 13px;
      color: var(--muted);
      display: none;
    }

    .empty-state {
      text-align: center;
      padding: 2rem 0;
      color: var(--muted);
      font-size: 14px;
    }

    py-terminal { display: none !important; }
  </style>
</head>
<body>
<div class="container">
  <header>
    <h1>GPA Calculator</h1>
    <p>Enter your courses to calculate weighted and unweighted GPA</p>
  </header>

  <div class="col-labels">
    <span>Course name</span>
    <span>Grade</span>
    <span>Course type</span>
    <span></span>
  </div>

  <div id="courses-list">
    <div class="empty-state" id="empty-msg">No courses yet — add one below</div>
  </div>

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

from pyscript import document
from pyodide.ffi import create_proxy

courses = []    
next_id = [1]  


UNWEIGHTED = {"A": 4, "B": 3, "C": 2, "D": 1, "F": 0}
WEIGHTED = {
    "Regular": {"A": 4, "B": 3, "C": 2, "D": 1, "F": 0},
    "Honors":  {"A": 5, "B": 4, "C": 3, "D": 2, "F": 1},
    "AP":      {"A": 5, "B": 4, "C": 3, "D": 2, "F": 1},
}


def calculate_gpa(course_list):
    if len(course_list) == 0:
        return None, None
    uw_total = 0  
    w_total  = 0  

    for course in course_list:
        uw_total += UNWEIGHTED[course["grade"]]
        w_total  += WEIGHTED[course["type"]][course["grade"]]

    unweighted_gpa = round(uw_total / len(course_list), 2)
    weighted_gpa   = round(w_total  / len(course_list), 2)

    return unweighted_gpa, weighted_gpa

def calculate_and_display():
    uw, w = calculate_gpa(courses)  

    uw_el   = document.getElementById("uw-gpa")
    w_el    = document.getElementById("w-gpa")
    sum_el  = document.getElementById("summary")
    sum_txt = document.getElementById("summary-text")

    if uw is None:
        uw_el.textContent    = "—"
        w_el.textContent     = "—"
        sum_el.style.display = "none"
    else:
        uw_el.textContent = f"{uw:.2f}"
        w_el.textContent  = f"{w:.2f}"

        ap_count     = sum(1 for c in courses if c["type"] == "AP")
        honors_count = sum(1 for c in courses if c["type"] == "Honors")
        boost        = round(w - uw, 2)
        count        = len(courses)

        parts = [f"{count} course{'s' if count != 1 else ''}"]
        if ap_count:     parts.append(f"{ap_count} AP")
        if honors_count: parts.append(f"{honors_count} Honors")
        parts.append(f"weighting boost +{boost:.2f}")

        sum_txt.textContent  = "  ·  ".join(parts)
        sum_el.style.display = "block"


def render_courses():
    list_el = document.getElementById("courses-list")
    list_el.innerHTML = ""


    if len(courses) == 0:
        empty = document.createElement("div")
        empty.className = "empty-state"
        empty.id = "empty-msg"
        empty.textContent = "No courses yet — add one below"
        list_el.appendChild(empty)
        return

    for course in courses:
        cid = course["id"]

        row = document.createElement("div")
        row.className = "course-row"
        row.id = f"course-{cid}"


        name_input = document.createElement("input")
        name_input.type = "text"
        name_input.placeholder = "e.g. English"
        name_input.value = course["name"]

        def make_name_handler(course_id):
            def handler(ev):
                update_field(course_id, "name", ev.target.value)
            return handler
        name_input.addEventListener("input", create_proxy(make_name_handler(cid)))

    
        grade_sel = document.createElement("select")
        for g in ["A", "B", "C", "D", "F"]:
            opt = document.createElement("option")
            opt.value = g
            opt.textContent = g
            if course["grade"] == g:
                opt.selected = True
            grade_sel.appendChild(opt)

        def make_grade_handler(course_id):
            def handler(ev):
                update_field(course_id, "grade", ev.target.value)
            return handler
        grade_sel.addEventListener("change", create_proxy(make_grade_handler(cid)))

    
        type_sel = document.createElement("select")
        for t in ["Regular", "Honors", "AP"]:
            opt = document.createElement("option")
            opt.value = t
            opt.textContent = t
            if course["type"] == t:
                opt.selected = True
            type_sel.appendChild(opt)

        def make_type_handler(course_id):
            def handler(ev):
                update_field(course_id, "type", ev.target.value)
            return handler
        type_sel.addEventListener("change", create_proxy(make_type_handler(cid)))


        del_btn = document.createElement("button")
        del_btn.className = "del-btn"
        del_btn.textContent = "×"
        del_btn.title = "Remove"

        def make_del_handler(course_id):
            def handler(ev):
                remove_course(course_id)
            return handler
        del_btn.addEventListener("click", create_proxy(make_del_handler(cid)))

        row.appendChild(name_input)
        row.appendChild(grade_sel)
        row.appendChild(type_sel)
        row.appendChild(del_btn)
        list_el.appendChild(row)


def add_course(event=None):
    cid = next_id[0]
    next_id[0] += 1
    courses.append({"id": cid, "name": "", "grade": "A", "type": "Regular"})
    render_courses()
    calculate_and_display()


def remove_course(course_id):
    for i, c in enumerate(courses):
        if c["id"] == course_id:
            courses.pop(i)
            break
    render_courses()
    calculate_and_display()


def update_field(course_id, field, value):
    for c in courses:
        if c["id"] == course_id:
            c[field] = value   # SELECTION — update only the named field
            break
    calculate_and_display()

document.getElementById("add-btn").addEventListener("click", create_proxy(add_course))

add_course()
add_course()
add_course()
</script>
</body>
</html>