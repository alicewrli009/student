---
permalink: /ppr
---

## Personalized Project Reference
# First Code Segment: Student-Developed Procedure
 ```
 function displayTheses(data) {
    const thesisOutput = document.getElementById('thesis-output');
    const recommendationsOutput = document.getElementById('thesis-recommendations');
    
    // SEQUENCING: Clear previous output first
    thesisOutput.innerHTML = '';

    // SELECTION: Check if data exists
    if (!data.theses || data.theses.length === 0) {
        thesisOutput.innerHTML = '<p>No theses generated. Please try again.</p>';
        return;
    }

    // ITERATION: Loop through each thesis
    data.theses.forEach((thesis) => {
        // SELECTION: Determine strength class based on score
        const strengthClass = thesis.strength >= 8 ? 'thesis-strength-high' : 
                             thesis.strength >= 6 ? 'thesis-strength-medium' : 
                             'thesis-strength-low';
        
        const card = document.createElement('div');
        card.className = 'thesis-card';
        card.innerHTML = `
            <div class="thesis-statement">${thesis.statement}</div>
            <span class="thesis-strength-badge ${strengthClass}">Strength: ${thesis.strength}/10</span>
            <p style="color: #c8d7eb; margin-top: 10px; font-size: 0.9rem;">${thesis.strengthExplanation}</p>
            
            ${thesis.supportingArguments && thesis.supportingArguments.length > 0 ? `
                <div class="thesis-details">
                    <h5>Supporting Arguments</h5>
                    <ul>
                        ${thesis.supportingArguments.map(arg => `<li>${arg}</li>`).join('')}
                    </ul>
                </div>
            ` : ''}
            
            ${thesis.counterarguments && thesis.counterarguments.length > 0 ? `
                <div class="thesis-details">
                    <h5>Counterarguments to Address</h5>
                    <ul>
                        ${thesis.counterarguments.map(counter => `<li>${counter}</li>`).join('')}
                    </ul>
                </div>
            ` : ''}
            
            <button class="thesis-btn-use" data-statement="${thesis.statement.replace(/"/g, '&quot;')}">
                Use This Thesis
            </button>
        `;
        
        thesisOutput.appendChild(card);
    });

    // Add event listeners to "Use This Thesis" buttons
    document.querySelectorAll('.thesis-btn-use').forEach(btn => {
        btn.addEventListener('click', function() {
            const statement = this.getAttribute('data-statement');
            useThesis(statement);
        });
    });

    // SELECTION: Display recommendations if available
    if (data.recommendations) {
        recommendationsOutput.innerHTML = `
            <div class="thesis-recommendations">
                <h5>Recommendations</h5>
                <p>${data.recommendations}</p>
            </div>
        `;
    }
}
```

