---
permalink: ppr
---
<!-- Section 2: Thesis Generator -->
        <div class="section-container" id="section-2">
            <div class="section-header">
                <h2 class="section-title">Thesis Generator</h2>
                <p class="section-description">
                Starting your essay can be challenging. Use this AI-powered tool to 
                generate strong thesis statements that outline your argument effectively.
                </p>
            </div>

            <div class="content-placeholder">
                <p>
<style>
        .thesis-gen-card {
            background: #a7a0d4;
            border: 1px solid rgba(255,255,255,0.08);
            border-radius: 12px;
            padding: 24px;
            margin: 30px 0;
            color: #eaf6ff;
            box-shadow: 0 12px 30px rgba(0,0,0,0.25);
        }

        .thesis-gen-card h3 {
            margin: 0 0 12px 0;
            color: #e4f1ff;
            font-size: 1.5rem;
        }

        .thesis-gen-card p {
            margin: 0 0 16px 0;
            color: #c8d7eb;
            font-size: 0.95rem;
        }

        .thesis-form-group {
            margin-bottom: 16px;
        }

        .thesis-label {
            display: block;
            font-weight: 600;
            margin-bottom: 6px;
            color: #38457f;
            font-size: 1.05rem;
        }

        .thesis-input,
        .thesis-textarea,
        .thesis-select {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: 1px solid rgba(255,255,255,0.1);
            background: rgba(255,255,255,0.05);
            color: #23256a;
            font-family: inherit;
            font-size: 0.95rem;
            box-sizing: border-box;
        }

        .thesis-textarea {
            min-height: 80px;
            resize: vertical;
        }

        .thesis-input::placeholder,
        .thesis-textarea::placeholder {
            color: rgba(234, 246, 255, 0.4);
        }

        .thesis-input:focus,
        .thesis-textarea:focus,
        .thesis-select:focus {
            outline: none;
            border-color: #7ad2f9;
            background: rgba(255,255,255,0.08);
        }

        .thesis-points-container {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .thesis-point-row {
            display: flex;
            gap: 8px;
            align-items: center;
        }

        .thesis-point-row input {
            flex: 1;
        }

        .thesis-btn-remove {
            padding: 8px 12px;
            background: rgba(248, 113, 113, 0.2);
            border: 1px solid rgba(248, 113, 113, 0.3);
            color: #fca5a5;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s;
        }

        .thesis-btn-remove:hover {
            background: rgba(248, 113, 113, 0.3);
        }

        .thesis-btn-add {
            margin-top: 8px;
            padding: 8px 14px;
            background: rgba(155, 231, 196, 0.15);
            border: 1px solid rgba(155, 231, 196, 0.3);
            color: #9be7c4;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s;
        }

        .thesis-btn-add:hover {
            background: rgba(155, 231, 196, 0.25);
        }

        .thesis-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .thesis-btn {
            flex: 1;
            min-width: 140px;
            padding: 12px 16px;
            border: none;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.2s;
            font-size: 0.95rem;
        }

        .thesis-btn-primary {
            background: #7ad2f9;
            color: #0e2038;
        }

        .thesis-btn-secondary {
            background: rgba(255,255,255,0.1);
            color: #d6e6ff;
            border: 1px solid rgba(255,255,255,0.15);
        }

        .thesis-btn:hover {
            transform: translateY(-1px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }

        .thesis-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        .thesis-status {
            margin-top: 12px;
            padding: 10px;
            border-radius: 8px;
            font-weight: 600;
            display: none;
        }

        .thesis-status.success {
            background: rgba(155, 231, 196, 0.15);
            border: 1px solid rgba(155, 231, 196, 0.3);
            color: #9be7c4;
        }

        .thesis-status.error {
            background: rgba(248, 113, 113, 0.15);
            border: 1px solid rgba(248, 113, 113, 0.3);
            color: #fca5a5;
        }

        .thesis-status.info {
            background: rgba(122, 210, 249, 0.15);
            border: 1px solid rgba(122, 210, 249, 0.3);
            color: #7ad2f9;
        }

        .thesis-output-section {
            margin-top: 24px;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .thesis-output-section h4 {
            color: #e4f1ff;
            margin-bottom: 16px;
            font-size: 1.2rem;
        }

        .thesis-card {
            background: rgba(0,0,0,0.2);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 10px;
            padding: 16px;
            margin-bottom: 16px;
        }

        .thesis-statement {
            font-size: 1.05rem;
            font-weight: 600;
            color: #e4f1ff;
            margin-bottom: 12px;
            line-height: 1.5;
        }

        .thesis-strength-badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .thesis-strength-high {
            background: rgba(155, 231, 196, 0.3);
            color: #9be7c4;
            border: 1px solid rgba(155, 231, 196, 0.4);
        }

        .thesis-strength-medium {
            background: rgba(251, 191, 36, 0.3);
            color: #fbbf24;
            border: 1px solid rgba(251, 191, 36, 0.4);
        }

        .thesis-strength-low {
            background: rgba(248, 113, 113, 0.3);
            color: #fca5a5;
            border: 1px solid rgba(248, 113, 113, 0.4);
        }

        .thesis-details {
            margin-top: 12px;
            padding-top: 12px;
            border-top: 1px solid rgba(255,255,255,0.08);
        }

        .thesis-details h5 {
            color: #7ad2f9;
            margin-bottom: 8px;
            font-size: 0.9rem;
        }

        .thesis-details ul {
            list-style-position: inside;
            color: #c8d7eb;
            font-size: 0.9rem;
            margin: 0;
            padding-left: 8px;
        }

        .thesis-details li {
            margin-bottom: 6px;
        }

        .thesis-btn-use {
            margin-top: 12px;
            padding: 8px 14px;
            background: rgba(122, 210, 249, 0.2);
            border: 1px solid rgba(122, 210, 249, 0.3);
            color: #7ad2f9;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s;
        }

        .thesis-btn-use:hover {
            background: rgba(122, 210, 249, 0.3);
        }

        .thesis-loading {
            text-align: center;
            padding: 30px;
        }

        .thesis-spinner {
            border: 3px solid rgba(255,255,255,0.1);
            border-top: 3px solid #7ad2f9;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: thesis-spin 1s linear infinite;
            margin: 0 auto 16px;
        }

        @keyframes thesis-spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .thesis-recommendations {
            background: rgba(251, 191, 36, 0.15);
            border-left: 3px solid #fbbf24;
            padding: 14px;
            margin-top: 16px;
            border-radius: 8px;
        }

        .thesis-recommendations h5 {
            color: #fbbf24;
            margin: 0 0 8px 0;
            font-size: 0.95rem;
        }

        .thesis-recommendations p {
            color: #e6f0ff;
            margin: 0;
            font-size: 0.9rem;
        }
    </style>
    <div class="thesis-gen-card">

        <div class="thesis-form-group">
            <label class="thesis-label" for="thesis-topic">Topic *</label>
            <input type="text" id="thesis-topic" class="thesis-input" placeholder="e.g., Social Media Impact on Society" required>
        </div>

        <div class="thesis-form-group">
            <label class="thesis-label" for="thesis-position">Your Position/Argument *</label>
            <textarea id="thesis-position" class="thesis-textarea" placeholder="e.g., Social media has negative effects on mental health" required></textarea>
        </div>

        <div class="thesis-form-group">
            <label class="thesis-label">Supporting Points (Optional)</label>
            <div class="thesis-points-container" id="thesis-points-container">
                <div class="thesis-point-row">
                    <input type="text" class="thesis-input thesis-supporting-point" placeholder="Supporting point 1">
                </div>
            </div>
            <button class="thesis-btn-add" id="thesis-add-point">+ Add Point</button>
        </div>

        <div class="thesis-form-group">
            <label class="thesis-label" for="thesis-type">Thesis Type</label>
            <select id="thesis-type" class="thesis-select">
                <option value="Argumentative">Argumentative</option>
                <option value="Analytical">Analytical</option>
                <option value="Expository">Expository</option>
                <option value="Compare/Contrast">Compare/Contrast</option>
                <option value="Cause/Effect">Cause/Effect</option>
            </select>
        </div>

        <div class="thesis-form-group">
            <label class="thesis-label" for="thesis-audience">Target Audience (Optional)</label>
            <input type="text" id="thesis-audience" class="thesis-input" placeholder="e.g., General academic">
        </div>

        <div class="thesis-actions">
            <button class="thesis-btn thesis-btn-primary" id="thesis-generate">Generate Thesis</button>
            <button class="thesis-btn thesis-btn-secondary" id="thesis-clear">🔄 Clear Form</button>
        </div>

        <div id="thesis-status" class="thesis-status"></div>

        <div class="thesis-output-section" id="thesis-output-section" style="display: none;">
            <h4>Generated Thesis Statements</h4>
            <div id="thesis-output"></div>
            <div id="thesis-recommendations"></div>
        </div>
    </div>

<script type="module">
    import {pythonURI} from '{{site.baseurl}}/assets/js/api/config.js';

    const API_BASE = pythonURI;

    function addThesisPoint() {
        const container = document.getElementById('thesis-points-container');
        const pointDiv = document.createElement('div');
        pointDiv.className = 'thesis-point-row';
        pointDiv.innerHTML = `
            <input type="text" class="thesis-input thesis-supporting-point" placeholder="Supporting point ${container.children.length + 1}">
            <button class="thesis-btn-remove" onclick="removeThesisPoint(this)">×</button>
        `;
        container.appendChild(pointDiv);
    }

    window.removeThesisPoint = function(btn) {
        btn.parentElement.remove();
    };

    function showThesisStatus(message, type) {
        const statusDiv = document.getElementById('thesis-status');
        statusDiv.textContent = message;
        statusDiv.className = `thesis-status ${type}`;
        statusDiv.style.display = 'block';
        
        if (type !== 'info') {
            setTimeout(() => statusDiv.style.display = 'none', 5000);
        }
    }

    async function generateThesis() {
        const topic = document.getElementById('thesis-topic').value.trim();
        const position = document.getElementById('thesis-position').value.trim();
        
        if (!topic || !position) {
            showThesisStatus('Please fill in both Topic and Position fields', 'error');
            return;
        }

        const pointInputs = document.querySelectorAll('.thesis-supporting-point');
        const supportingPoints = Array.from(pointInputs)
            .map(input => input.value.trim())
            .filter(point => point.length > 0);

        const thesisType = document.getElementById('thesis-type').value;
        const audience = document.getElementById('thesis-audience').value.trim();

        const outputSection = document.getElementById('thesis-output-section');
        const thesisOutput = document.getElementById('thesis-output');
        outputSection.style.display = 'block';
        thesisOutput.innerHTML = '<div class="thesis-loading"><div class="thesis-spinner"></div><p>Generating your thesis statements...</p></div>';

        try {
            const response = await fetch(`${API_BASE}/api/thesis/generate`, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    topic: topic,
                    position: position,
                    supportingPoints: supportingPoints,
                    thesisType: thesisType,
                    audience: audience
                })
            });

            if (!response.ok) {
                const errorData = await response.json().catch(() => ({}));
                throw new Error(errorData.error || `HTTP ${response.status}: ${response.statusText}`);
            }

            const result = await response.json();
            
            if (!result.success || !result.data) {
                throw new Error('Invalid response from server');
            }

            displayTheses(result.data);
            showThesisStatus('✅ Thesis statements generated successfully!', 'success');
        } catch (error) {
            console.error('Error:', error);
            thesisOutput.innerHTML = '';
            outputSection.style.display = 'none';
            showThesisStatus('❌ Error: ' + error.message, 'error');
        }
    }

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

        // Add event yes listeners to "Use This Thesis" buttons
        document.querySelectorAll('.thesis-btn-use').forEach(btn => {
            btn.addEventListener('click', function() {
                const statement = this.getAttribute('data-statement');
                useThesis(statement);
            });
        });

        if (data.recommendations) {
            recommendationsOutput.innerHTML = `
                <div class="thesis-recommendations">
                    <h5>Recommendations</h5>
                    <p>${data.recommendations}</p>
                </div>
            `;
        }
    }

    function useThesis(statement) {
        navigator.clipboard.writeText(statement).then(() => {
            showThesisStatus('Thesis copied to clipboard!', 'success');
        }).catch(() => {
            showThesisStatus('Please manually copy the thesis', 'error');
        });
    }

    function clearThesisForm() {
        document.getElementById('thesis-topic').value = '';
        document.getElementById('thesis-position').value = '';
        document.getElementById('thesis-audience').value = '';
        document.getElementById('thesis-type').value = 'Argumentative';
        
        const pointsContainer = document.getElementById('thesis-points-container');
        pointsContainer.innerHTML = `
            <div class="thesis-point-row">
                <input type="text" class="thesis-input thesis-supporting-point" placeholder="Supporting point 1">
            </div>
        `;
        
        document.getElementById('thesis-output-section').style.display = 'none';
        showThesisStatus('Form cleared', 'info');
    }

    // Event listeners
    document.getElementById('thesis-add-point').addEventListener('click', addThesisPoint);
    document.getElementById('thesis-generate').addEventListener('click', generateThesis);
    document.getElementById('thesis-clear').addEventListener('click', clearThesisForm);
</script>
</p>
                <p style="margin-top: 20px; font-size: 0.9rem;">
                </p>
            </div>

            <div class="navigation-buttons">
                <button class="nav-btn nav-btn-prev" onclick="prevSection()">
                    ← Previous
                </button>
                <button class="nav-btn nav-btn-next" onclick="nextSection()">
                    Next Section →
                </button>
            </div>
        </div>