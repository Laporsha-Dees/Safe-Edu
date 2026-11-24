# Safe Edu

**A school AI study assistant that learns only from teacher-provided materials and follows each teacher's rules.**

Safe Edu is a capstone project from the **UN Women Young Feminist AI School**. This repository holds a clickable prototype (MVP) of the platform for a high school setting.

> **Status:** prototype for demonstration. The chatbot replies are scripted, and nothing is saved between page loads. See [What's real and what's a placeholder](#whats-real-and-whats-a-placeholder).

---

## The problem

When students use general-purpose AI without guidance, they can skip the reading, writing and problem-solving that build those skills. They also get answers drawn from the open internet rather than from what their class is actually studying.

## The idea

Safe Edu gives schools an AI study assistant that:

- **Uses only school-provided materials.** Teachers choose which readings and assignments it can draw on, and it has no live internet access.
- **Puts teachers in control.** Each teacher decides how the assistant responds: giving hints instead of answers, giving feedback on drafts, or quizzing students for practice.
- **Is transparent with students.** Students see what the assistant will and won't do, who can read their chats, and which work they should do without AI help.
- **Takes student rights seriously.** Consent, privacy and data use are part of the design from the start, with extra care because the users are young people.

---

## Try it

**Live demo:** _add your GitHub Pages link here_

**Run it locally:** download `index.html` and open it in any web browser. Nothing needs to be installed.

Use the **Teacher / Student** switch at the top right to move between the two views.

### Suggested demo walkthrough

1. **Teacher → Chatbot settings.** Open *2. How should the assistant respond?* to see the response styles, the private instructions for the assistant, and the official description students will see.
2. **Teacher → Biology · Period 2 → Materials.** See the units. Click **Upload material** to post an assignment with a unit, type, due date, graded setting and study-assistant access.
3. **Student → Biology.** Filter and group classwork by status, unit or type, and turn in an assignment with files.
4. **Student → Study assistant.** Click *"What's the answer to #3?"* The assistant responds with a hint that points back to the reading instead of giving the answer.
5. **Back in Teacher → Chatbot settings,** change the response styles, click **Preview as student**, and ask again.

---

## Features in the prototype

### Teacher view
- **Class periods** with three tabs:
  - **Student roster**, including each student's consent status for using the AI assistant
  - **Grades**
  - **Materials**
- **Units** that the teacher creates and shares across all their periods.
- **Uploading and editing materials,** with these settings for each one:
  - unit and type (Classwork, Homework, Project, Quiz, Reading, Other)
  - graded or not graded
  - due date, or no due date
  - instructions for students
  - whether the study assistant can use it
  - which periods to post it to
- **Chatbot settings:**
  1. **Class and materials:** turn the assistant's access to each material on or off.
  2. **How should the assistant respond?** Turn on one or more response styles (Hint-only, Feedback, Practice). Write private instructions for the assistant and an official description that students see.
  3. **Guardrails:** reading level, no final answers, stay within class materials, redirect off-topic questions, and an optional flag for safety concerns.

### Student view
- **Class pages** that show what the teacher posted, with to do / overdue / completed counts.
- **Organizing tools:**
  - filter by status, unit or type
  - sort by due date, recently added or title
  - group by unit, type or status
- **Turning in work:** upload files and add a note to the teacher for classwork, homework and projects. Readings and other items can be marked done.
- **Study assistant:**
  - Each conversation is tied to one class, so the right teacher's rules apply.
  - Saved chats are grouped by class.
  - The teacher's description of the assistant is shown at the top.
  - A privacy panel names who can read the chats, alongside consent status.

---

## What's real and what's a placeholder

| Works in the prototype | Placeholder for now |
|---|---|
| Moving between all teacher and student pages | Chatbot replies are pre-written scripts, not a live AI model |
| Teacher settings change what students see | Private instructions and reading level don't change the scripted replies yet |
| Response styles change which scripted reply is shown | Only the Biology class has scripted replies; History and English show placeholder replies |
| Creating units and uploading or editing materials | Uploaded files aren't read or stored, only their names |
| Student filtering, sorting, grouping and turn-ins | Everything resets when the page reloads |
| Overdue status based on today's date | Teachers can't view student submissions yet |
| | Names, grades and consent statuses are made up |

---

## Customizing the demo

Everything is in one file, `index.html`. The editable content is in clearly labeled blocks at the top of the `<script>` section:

| Block | What it controls |
|---|---|
| `LESSON` | The reading the study assistant answers from |
| `SCRIPTS`, `CHIPS` | Scripted assistant replies and the example questions shown to students |
| `TEACHER`, `BIO_UNITS`, `baseMaterials`, `PERIODS` | Teacher name, units, materials, rosters and grades |
| `STUDENT_NAME`, `CLASSES`, `SAVED_CHATS` | The student's name, classes and saved chats |
| `MODES` | Response styles and their descriptions |

---

## Responsible AI considerations

This prototype is a starting point for a larger question: **how can schools adopt AI responsibly with young people?**

- **Consent and assent:** a parent or guardian consents and the student agrees before using the assistant. The roster shows this status.
- **Privacy:** each class's chats are visible only to that class's teacher. Chats have a clear retention period and are never sold or used to train AI. The policy shown in the prototype is an example.
- **Transparency:** students see what the assistant is, what it can and can't do, and which work to do without it.
- **Grounding, honestly described:** the assistant is limited to class materials and has no live web access. However, any AI model learned from broad data during training, so "grounded in school materials" is the accurate claim, not "disconnected from the internet." A fully self-hosted model is a possible future direction.

---

## Roadmap

- Connect a real AI model, grounded in each class's approved materials (retrieval-augmented generation)
- Let teachers view, comment on and grade student submissions
- Build an **administrator interface** for school-wide policies, approved tools, data retention and consent management
- Real accounts and saved data, built with student privacy laws in mind (for example, FERPA in the US)
- Test with teachers and students, including whether the assistant actually supports learning rather than replacing it
- Accessibility review and support for multilingual learners

---

## Credits

- **Project:** Laporsha Dees, UN Women Young Feminist AI School capstone
- **Sample curriculum:** unit and lesson titles in the Biology demo follow the [Biology Corner Intro Biology course](https://www.biologycorner.com/introbio/index.html) by Shannan Muskopf. Descriptions in this prototype are original, and no Biology Corner materials are reproduced. Visit Biology Corner for the full lessons.
- The sample reading ("Cells and Their Organelles"), all student and teacher names, and all grades are invented for this prototype.
- Built with help from Claude (Anthropic).
