---
permalink: /skillc
---

# AP CSP Create Task — Code Segments

---

## Procedure (3b)

### i. Student-Developed Procedure

```javascript
function displayTheses(data) {
    const thesisOutput = document.getElementById('thesis-output');
    const recommendationsOutput = document.getElementById('thesis-recommendations');
    
    thesisOutput.innerHTML = '';

    if (!data.theses || data.theses.length === 0) {
        thesisOutput.innerHTML = '<p>No theses generated. Please try again.</p>';
        return;
    }

    data.theses.forEach((thesis) => {
        const strengthClass = thesis.strength >= 8 ? 'thesis-strength-high' : 
                             thesis.strength >= 6 ? 'thesis-strength-medium' : 'thesis-strength-low';
        
        const card = document.createElement('div');
        card.className = 'thesis-card';
        card.innerHTML = `
            <div class="thesis-statement">${thesis.statement}</div>
            <span class="thesis-strength-badge ${strengthClass}">Strength: ${thesis.strength}/10</span>
            ...
        `;
        thesisOutput.appendChild(card);
    });

    if (data.recommendations) {
        recommendationsOutput.innerHTML = `...`;
    }
}
```

This procedure (`displayTheses`) takes the parameter `data`, which directly controls what gets rendered. It uses **sequencing** (clearing output, then building cards), **selection** (the ternary chain choosing `strengthClass`, and the `if` guard for empty theses), and **iteration** (`forEach` looping over each thesis).

---

### ii. Call to the Procedure

```javascript
const result = await response.json();

if (!result.success || !result.data) {
    throw new Error('Invalid response from server');
}

displayTheses(result.data);
showThesisStatus('✅ Thesis statements generated successfully!', 'success');
```
const result = await response.json() — takes the raw HTTP response and parses it from JSON into a usable JavaScript object, storing it in result. The await means the program pauses here until that conversion finishes.
The if block — this is a validation check. It's asking: "did the server actually return what we expected?" If result.success is false/missing, or result.data is empty/missing, something went wrong, so it throws an error and stops execution rather than trying to display broken data.
displayTheses(result.data) — this is the actual call to your student-developed procedure. It passes result.data (the thesis statements and recommendations from the server) as the argument, which becomes the data parameter inside displayTheses. This is why it qualifies as "a call to the procedure" — it's the moment the procedure gets invoked with real data.
showThesisStatus(...) — after successfully calling displayTheses, this shows a green confirmation message to the user.

---

## List (3c)

### i. Data Stored in the List

```javascript
const pointInputs = document.querySelectorAll('.thesis-supporting-point');
const supportingPoints = Array.from(pointInputs)
    .map(input => input.value.trim())
    .filter(point => point.length > 0);
```

Here, `supportingPoints` is a list (array) built by collecting every user-entered supporting point input, transforming each to a trimmed string, and filtering out any blank entries.

---

### ii. List Being Used

```javascript
body: JSON.stringify({
    topic: topic,
    position: position,
    supportingPoints: supportingPoints,
    thesisType: thesisType,
    audience: audience
})
```

The `supportingPoints` list is then passed as part of the API request body, where the backend uses all of its elements together to inform the AI-generated thesis statements. Without the list, the program would have no way to send a variable number of user-provided points to the server — using a list here manages the complexity of handling an unknown quantity of inputs as a single, organized unit.