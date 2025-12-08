---
layout: post
title: API Create
permalink: /thesis
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Thesis Generator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }

        .content {
            padding: 40px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: 600;
            margin-bottom: 8px;
            color: #333;
            font-size: 14px;
        }

        input[type="text"],
        textarea,
        select {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 14px;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        input[type="text"]:focus,
        textarea:focus,
        select:focus {
            outline: none;
            border-color: #667eea;
        }

        textarea {
            resize: vertical;
            min-height: 80px;
        }

        .points-container {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .point-input {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .point-input input {
            flex: 1;
        }

        .btn-remove {
            background: #ff4757;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 6px;
            cursor: pointer;
        }

        .btn-add {
            background: #2ed573;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 10px;
        }

        .button-group {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        button {
            padding: 14px 28px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
        }

        .btn-secondary {
            background: #f1f2f6;
            color: #2f3542;
        }

        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .status-message {
            padding: 15px;
            border-radius: 8px;
            margin: 20px 0;
            display: none;
        }

        .output-section {
            margin-top: 40px;
            padding-top: 40px;
            border-top: 2px solid #e0e0e0;
        }

        .output-section h2 {
            color: #2f3542;
            margin-bottom: 25px;
            font-size: 1.8em;
        }

        .thesis-card {
            background: #f8f9fa;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            padding: 25px;
            margin-bottom: 20px;
        }

        .thesis-statement {
            font-size: 1.2em;
            font-weight: 600;
            color: #2f3542;
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .strength-badge {
            display: inline-block;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .strength-high { background: #2ed573; color: white; }
        .strength-medium { background: #ffa502; color: white; }
        .strength-low { background: #ff4757; color: white; }

        .thesis-details {
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid #ddd;
        }

        .thesis-details h4 {
            color: #667eea;
            margin-bottom: 10px;
            font-size: 14px;
        }

        .thesis-details ul {
            list-style-position: inside;
            color: #555;
        }

        .thesis-details li {
            margin-bottom: 8px;
        }

        .btn-use-thesis {
            background: #667eea;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 15px;
        }

        .loading {
            text-align: center;
            padding: 40px;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #667eea;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .recommendations {
            background: #fff3cd;
            border-left: 4px solid #ffa502;
            padding: 20px;
            margin-top: 20px;
            border-radius: 8px;
        }

        .recommendations h3 {
            color: #856404;
            margin-bottom: 10px;
        }

        .debug-info {
            background: #f0f0f0;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            font-family: monospace;
            font-size: 12px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🎓 AI Thesis Generator</h1>
            <p>Transform your ideas into powerful thesis statements</p>
        </div>

        <div class="content">
            <div class="form-group">
                <label for="topic">Topic *</label>
                <input type="text" id="topic" placeholder="e.g., Social Media Impact on Society" required>
            </div>

            <div class="form-group">
                <label for="position">Your Position/Argument *</label>
                <textarea id="position" placeholder="e.g., Social media has negative effects on mental health" required></textarea>
            </div>

            <div class="form-group">
                <label>Supporting Points (Optional)</label>
                <div class="points-container" id="pointsContainer">
                    <div class="point-input">
                        <input type="text" class="supporting-point" placeholder="Supporting point 1">
                    </div>
                </div>
                <button class="btn-add" onclick="addPoint()">+ Add Point</button>
            </div>

            <div class="form-group">
                <label for="thesisType">Thesis Type</label>
                <select id="thesisType">
                    <option value="Argumentative">Argumentative</option>
                    <option value="Analytical">Analytical</option>
                    <option value="Expository">Expository</option>
                    <option value="Compare/Contrast">Compare/Contrast</option>
                    <option value="Cause/Effect">Cause/Effect</option>
                </select>
            </div>

            <div class="form-group">
                <label for="audience">Target Audience (Optional)</label>
                <input type="text" id="audience" placeholder="e.g., General academic">
            </div>

            <div class="button-group">
                <button class="btn-primary" onclick="generateThesis()">✨ Generate Thesis</button>
                <button class="btn-secondary" onclick="clearForm()">🔄 Clear Form</button>
            </div>

            <div id="statusMessage" class="status-message"></div>
            <div id="debugInfo" class="debug-info" style="display: none;"></div>

            <div class="output-section" id="outputSection" style="display: none;">
                <h2>Generated Thesis Statements</h2>
                <div id="thesesOutput"></div>
                <div id="recommendationsOutput"></div>
            </div>
        </div>
    </div>

    <script>
        // Auto-detect API URL based on current hostname
        const API_URL = `http://${window.location.hostname}:8587/api/thesis`;
        
        console.log('API URL:', API_URL);

        function addPoint() {
            const container = document.getElementById('pointsContainer');
            const pointDiv = document.createElement('div');
            pointDiv.className = 'point-input';
            pointDiv.innerHTML = `
                <input type="text" class="supporting-point" placeholder="Supporting point ${container.children.length + 1}">
                <button class="btn-remove" onclick="removePoint(this)">×</button>
            `;
            container.appendChild(pointDiv);
        }

        function removePoint(btn) {
            btn.parentElement.remove();
        }

        function showStatus(message, type) {
            const statusDiv = document.getElementById('statusMessage');
            statusDiv.textContent = message;
            statusDiv.style.display = 'block';
            
            const colors = {
                success: { bg: '#d4edda', color: '#155724', border: '#c3e6cb' },
                error: { bg: '#f8d7da', color: '#721c24', border: '#f5c6cb' },
                info: { bg: '#d1ecf1', color: '#0c5460', border: '#bee5eb' }
            };
            
            const style = colors[type] || colors.info;
            statusDiv.style.backgroundColor = style.bg;
            statusDiv.style.color = style.color;
            statusDiv.style.border = `1px solid ${style.border}`;
            
            setTimeout(() => statusDiv.style.display = 'none', 5000);
        }

        function showDebug(info) {
            const debugDiv = document.getElementById('debugInfo');
            debugDiv.textContent = JSON.stringify(info, null, 2);
            debugDiv.style.display = 'block';
        }

        async function generateThesis() {
            const topic = document.getElementById('topic').value.trim();
            const position = document.getElementById('position').value.trim();
            
            if (!topic || !position) {
                showStatus('Please fill in both Topic and Position fields', 'error');
                return;
            }

            const pointInputs = document.querySelectorAll('.supporting-point');
            const supportingPoints = Array.from(pointInputs)
                .map(input => input.value.trim())
                .filter(point => point.length > 0);

            const thesisType = document.getElementById('thesisType').value;
            const audience = document.getElementById('audience').value.trim();

            const outputSection = document.getElementById('outputSection');
            const thesesOutput = document.getElementById('thesesOutput');
            outputSection.style.display = 'block';
            thesesOutput.innerHTML = '<div class="loading"><div class="spinner"></div><p>Generating your thesis statements...</p></div>';

            const requestData = {
                topic,
                position,
                supportingPoints,
                thesisType,
                audience
            };

            console.log('Sending request:', requestData);
            console.log('To URL:', API_URL);

            try {
                const response = await fetch(API_URL, {
                    method: 'POST',
                    mode: 'cors',
                    headers: {
                        'Content-Type': 'application/json',
                        'Accept': 'application/json'
                    },
                    body: JSON.stringify(requestData)
                });

                console.log('Response status:', response.status);
                console.log('Response headers:', [...response.headers.entries()]);

                if (!response.ok) {
                    const errorText = await response.text();
                    console.error('Error response:', errorText);
                    throw new Error(`HTTP ${response.status}: ${errorText}`);
                }

                const result = await response.json();
                console.log('Success result:', result);

                if (result.success) {
                    displayTheses(result.data);
                    showStatus('✅ Thesis statements generated successfully!', 'success');
                } else {
                    throw new Error(result.error || 'Failed to generate thesis');
                }
            } catch (error) {
                console.error('Error details:', error);
                thesesOutput.innerHTML = '';
                outputSection.style.display = 'none';
                showStatus('❌ Error: ' + error.message, 'error');
                showDebug({
                    error: error.message,
                    stack: error.stack,
                    apiUrl: API_URL,
                    requestData
                });
            }
        }

        function displayTheses(data) {
            const thesesOutput = document.getElementById('thesesOutput');
            const recommendationsOutput = document.getElementById('recommendationsOutput');
            
            thesesOutput.innerHTML = '';

            if (!data.theses || data.theses.length === 0) {
                thesesOutput.innerHTML = '<p>No theses generated. Please try again.</p>';
                return;
            }

            data.theses.forEach((thesis) => {
                const strengthClass = thesis.strength >= 8 ? 'strength-high' : 
                                     thesis.strength >= 6 ? 'strength-medium' : 'strength-low';
                
                const card = document.createElement('div');
                card.className = 'thesis-card';
                card.innerHTML = `
                    <div class="thesis-statement">${thesis.statement}</div>
                    <span class="strength-badge ${strengthClass}">Strength: ${thesis.strength}/10</span>
                    <p style="color: #666; margin-top: 10px;">${thesis.strengthExplanation}</p>
                    
                    ${thesis.supportingArguments && thesis.supportingArguments.length > 0 ? `
                        <div class="thesis-details">
                            <h4>📚 Supporting Arguments</h4>
                            <ul>
                                ${thesis.supportingArguments.map(arg => `<li>${arg}</li>`).join('')}
                            </ul>
                        </div>
                    ` : ''}
                    
                    ${thesis.counterarguments && thesis.counterarguments.length > 0 ? `
                        <div class="thesis-details">
                            <h4>⚖️ Counterarguments to Address</h4>
                            <ul>
                                ${thesis.counterarguments.map(counter => `<li>${counter}</li>`).join('')}
                            </ul>
                        </div>
                    ` : ''}
                    
                    <button class="btn-use-thesis" onclick="useThesis(\`${thesis.statement.replace(/`/g, '\\`')}\`)">
                        Use This Thesis
                    </button>
                `;
                
                thesesOutput.appendChild(card);
            });

            if (data.recommendations) {
                recommendationsOutput.innerHTML = `
                    <div class="recommendations">
                        <h3>💡 Recommendations</h3>
                        <p>${data.recommendations}</p>
                    </div>
                `;
            }
        }

        function useThesis(statement) {
            navigator.clipboard.writeText(statement).then(() => {
                showStatus('📋 Thesis copied to clipboard!', 'success');
            }).catch(() => {
                showStatus('⚠️ Please manually copy the thesis', 'error');
            });
        }

        function clearForm() {
            document.getElementById('topic').value = '';
            document.getElementById('position').value = '';
            document.getElementById('audience').value = '';
            document.getElementById('thesisType').value = 'Argumentative';
            
            const pointsContainer = document.getElementById('pointsContainer');
            pointsContainer.innerHTML = `
                <div class="point-input">
                    <input type="text" class="supporting-point" placeholder="Supporting point 1">
                </div>
            `;
            
            document.getElementById('outputSection').style.display = 'none';
            document.getElementById('debugInfo').style.display = 'none';
            showStatus('Form cleared', 'info');
        }
    </script>
</body>
</html>