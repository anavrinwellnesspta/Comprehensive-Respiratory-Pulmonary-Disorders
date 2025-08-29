
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bioplasm NLS Respiratory & Pulmonary Disorders Protocol Database</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #0ea5e9 0%, #06b6d4 50%, #67e8f9 100%);
        }
        
        .card-hover {
            transition: all 0.3s ease;
        }
        
        .card-hover:hover {
            transform: translateY(-4px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        .category-copd { border-left: 4px solid #dc2626; }
        .category-asthma { border-left: 4px solid #f59e0b; }
        .category-fibrosis { border-left: 4px solid #7c3aed; }
        .category-pneumonia { border-left: 4px solid #059669; }
        .category-tuberculosis { border-left: 4px solid #0891b2; }
        .category-pulmonary-hypertension { border-left: 4px solid #be123c; }
        .category-sleep-apnea { border-left: 4px solid #9333ea; }
        
        .frequency-badge {
            background: linear-gradient(45deg, #0ea5e9, #06b6d4);
            color: white;
            padding: 2px 8px;
            border-radius: 12px;
            font-size: 0.75rem;
            font-weight: 500;
        }

        .severity-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            display: inline-block;
            margin-right: 8px;
        }

        .severity-mild { background-color: #22c55e; }
        .severity-moderate { background-color: #eab308; }
        .severity-severe { background-color: #ef4444; }

        .lung-icon {
            background: linear-gradient(45deg, #0ea5e9, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="gradient-bg text-white shadow-lg">
        <div class="max-w-7xl mx-auto px-4 py-6">
            <div class="flex items-center justify-between">
                <div class="flex items-center">
                    <div class="text-4xl mr-4">🫁</div>
                    <div>
                        <h1 class="text-3xl font-bold">Comprehensive Respiratory & Pulmonary Disorders Protocol Database</h1>
                        <p class="text-sky-100 mt-2">Complete Bioplasm NLS Protocols for All Major Respiratory & Lung Conditions</p>
                        <p class="text-sky-200 mt-1 text-sm">Created by Anavrin Wellness</p>
                    </div>
                </div>
                <div class="text-right">
                    <div class="text-sm text-sky-100">Comprehensive Edition</div>
                    <div class="text-sm text-sky-100">Updated: August 2025</div>
                </div>
            </div>
        </div>
    </header>

    <!-- Navigation & Search -->
    <div class="max-w-7xl mx-auto px-4 py-6">
        <div class="bg-white rounded-lg shadow-md p-6 mb-6">
            <div class="flex flex-col md:flex-row gap-4 items-center">
                <div class="flex-1">
                    <input type="text" id="searchInput" placeholder="Search comprehensive respiratory protocols by condition, symptoms, or body system..." 
                           class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500 focus:border-transparent">
                </div>
                <div class="flex gap-3">
                    <select id="categoryFilter" class="px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500">
                        <option value="">All Categories</option>
                        <option value="copd">COPD</option>
                        <option value="asthma">Asthma</option>
                        <option value="fibrosis">Pulmonary Fibrosis & ILD</option>
                        <option value="pneumonia">Pneumonia & Pleural</option>
                        <option value="tuberculosis">Tuberculosis & NTM</option>
                        <option value="pulmonary-hypertension">Pulmonary Hypertension & PE</option>
                        <option value="sleep-apnea">Sleep Apnea</option>
                    </select>
                    <select id="severityFilter" class="px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-500">
                        <option value="">All Severities</option>
                        <option value="mild">Mild</option>
                        <option value="moderate">Moderate</option>
                        <option value="severe">Severe</option>
                    </select>
                </div>
            </div>
        </div>

        <!-- Statistics Dashboard -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-8">
            <div class="bg-white rounded-lg shadow-md p-6">
                <div class="flex items-center">
                    <div class="p-3 rounded-full bg-sky-100 text-sky-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"></path>
                        </svg>
                    </div>
                    <div class="ml-4">
                        <p class="text-sm font-medium text-gray-600">Total Protocols</p>
                        <p class="text-2xl font-semibold text-gray-900" id="totalProtocols">42</p>
                    </div>
                </div>
            </div>
            
            <div class="bg-white rounded-lg shadow-md p-6">
                <div class="flex items-center">
                    <div class="p-3 rounded-full bg-blue-100 text-blue-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"></path>
                        </svg>
                    </div>
                    <div class="ml-4">
                        <p class="text-sm font-medium text-gray-600">Core Categories</p>
                        <p class="text-2xl font-semibold text-gray-900">7</p>
                    </div>
                </div>
            </div>
            
            <div class="bg-white rounded-lg shadow-md p-6">
                <div class="flex items-center">
                    <div class="p-3 rounded-full bg-green-100 text-green-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
                        </svg>
                    </div>
                    <div class="ml-4">
                        <p class="text-sm font-medium text-gray-600">Healing Frequencies</p>
                        <p class="text-2xl font-semibold text-gray-900">294</p>
                    </div>
                </div>
            </div>
            
            <div class="bg-white rounded-lg shadow-md p-6">
                <div class="flex items-center">
                    <div class="p-3 rounded-full bg-orange-100 text-orange-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                    </div>
                    <div class="ml-4">
                        <p class="text-sm font-medium text-gray-600">Avg Session</p>
                        <p class="text-2xl font-semibold text-gray-900">43min</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Respiratory Body Mapping Section -->
        <div class="bg-white rounded-lg shadow-md p-6 mb-8">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold text-gray-900">🫁 Comprehensive Respiratory & Pulmonary System Mapping</h2>
                <button id="toggleMapping" class="px-4 py-2 bg-sky-600 text-white rounded-lg hover:bg-sky-700 transition-colors">
                    Show Mapping Guide
                </button>
            </div>
            
            <div id="mappingContent" class="hidden">
                <p class="text-gray-600 mb-6">Complete understanding of all major respiratory and pulmonary system disorders for comprehensive NLS scanning and treatment protocols.</p>
                
                <!-- Comprehensive Respiratory Conditions Overview -->
                <div class="mb-6">
                    <h3 class="text-xl font-bold text-sky-800 mb-4">📊 Complete Respiratory Conditions NLS Database Mapping</h3>
                    <div class="overflow-x-auto">
                        <table class="w-full text-sm border-collapse border border-sky-300">
                            <thead>
                                <tr class="bg-sky-100">
                                    <th class="border border-sky-300 px-3 py-2 text-left font-semibold text-sky-800">Condition Category</th>
                                    <th class="border border-sky-300 px-3 py-2 text-left font-semibold text-sky-800">Primary System(s)</th>
                                    <th class="border border-sky-300 px-3 py-2 text-left font-semibold text-sky-800">Key NLS Focus Points</th>
                                    <th class="border border-sky-300 px-3 py-2 text-left font-semibold text-sky-800">Critical Etalons</th>
                                </tr>
                            </thead>
                            <tbody class="text-gray-700">
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">COPD & Genetic Deficiencies</td>
                                    <td class="border border-sky-300 px-3 py-2">Respiratory / Alveolar / Genetic</td>
                                    <td class="border border-sky-300 px-3 py-2">Alveoli, bronchi, protease balance, genetic markers</td>
                                    <td class="border border-sky-300 px-3 py-2">α-1 Antitrypsin, Elastin, Surfactant proteins, Gas exchange</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Asthma & Bronchial Disorders</td>
                                    <td class="border border-sky-300 px-3 py-2">Bronchial / Immune / Occupational</td>
                                    <td class="border border-sky-300 px-3 py-2">Bronchi, mast cells, triggers, workplace exposures</td>
                                    <td class="border border-sky-300 px-3 py-2">IgE, Eosinophils, Histamine, IL-4/5/13, Airway reactivity</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Interstitial Lung Diseases (ILD)</td>
                                    <td class="border border-sky-300 px-3 py-2">Interstitial / Occupational / Immune</td>
                                    <td class="border border-sky-300 px-3 py-2">Interstitium, granulomas, fibrosis, occupational particles</td>
                                    <td class="border border-sky-300 px-3 py-2">Collagen, TGF-β, ACE, Granuloma markers, Fibrotic progression</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Infections & Pleural Disorders</td>
                                    <td class="border border-sky-300 px-3 py-2">Alveolar / Pleural / Immune</td>
                                    <td class="border border-sky-300 px-3 py-2">Alveoli, pleural space, pathogens, immune response</td>
                                    <td class="border border-sky-300 px-3 py-2">Pathogen antigens, CRP, Procalcitonin, Pleural fluid markers</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Mycobacterial Diseases</td>
                                    <td class="border border-sky-300 px-3 py-2">Pulmonary / Immune / Granulomatous</td>
                                    <td class="border border-sky-300 px-3 py-2">Granulomas, immune surveillance, drug resistance</td>
                                    <td class="border border-sky-300 px-3 py-2">Mycobacterial antigens, IFN-γ, TNF-α, Drug resistance genes</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Pulmonary Vascular Diseases</td>
                                    <td class="border border-sky-300 px-3 py-2">Pulmonary Vascular / Cardiac / Thrombotic</td>
                                    <td class="border border-sky-300 px-3 py-2">Pulmonary vessels, right heart, clots, pressures</td>
                                    <td class="border border-sky-300 px-3 py-2">Endothelin-1, D-Dimer, BNP, Pulmonary pressures</td>
                                </tr>
                                <tr class="hover:bg-sky-50">
                                    <td class="border border-sky-300 px-3 py-2 font-medium">Sleep & Neurological Breathing</td>
                                    <td class="border border-sky-300 px-3 py-2">Upper Airway / Neurological / Sleep</td>
                                    <td class="border border-sky-300 px-3 py-2">Upper airway, brainstem, sleep architecture</td>
                                    <td class="border border-sky-300 px-3 py-2">O2/CO2 markers, Neural rhythm, Airway patency</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="space-y-6">
                        <div class="border border-sky-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-sky-800 mb-3">🫁 1. COPD & Genetic Respiratory Disorders</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Alveolar destruction and gas exchange impairment</li>
                                    <li>Protease-antiprotease imbalance (α-1 deficiency)</li>
                                    <li>Airway obstruction and respiratory muscle dysfunction</li>
                                    <li>Genetic markers and enzyme deficiencies</li>
                                </ul>
                            </div>
                            <div class="text-xs text-sky-600 bg-sky-50 p-2 rounded">
                                <strong>Focus:</strong> Airflow optimization, genetic enzyme support, and respiratory muscle strengthening.
                            </div>
                        </div>

                        <div class="border border-green-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-green-800 mb-3">🌬️ 2. Asthma & Occupational Lung Disease</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Bronchial hyperreactivity and smooth muscle constriction</li>
                                    <li>Allergic vs non-allergic inflammatory pathways</li>
                                    <li>Occupational sensitizers and chemical exposures</li>
                                    <li>Exercise-induced and environmental triggers</li>
                                </ul>
                            </div>
                            <div class="text-xs text-green-600 bg-green-50 p-2 rounded">
                                <strong>Focus:</strong> Trigger identification, bronchodilation, and occupational protection.
                            </div>
                        </div>

                        <div class="border border-purple-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-purple-800 mb-3">🔬 3. Interstitial Lung Diseases (ILD)</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Sarcoidosis with granulomatous inflammation</li>
                                    <li>Hypersensitivity pneumonitis from antigen exposure</li>
                                    <li>Pneumoconiosis from occupational particles (asbestos, silica)</li>
                                    <li>Idiopathic and secondary pulmonary fibrosis</li>
                                </ul>
                            </div>
                            <div class="text-xs text-purple-600 bg-purple-50 p-2 rounded">
                                <strong>Focus:</strong> Fibrosis control, granuloma modulation, and occupational exposure management.
                            </div>
                        </div>

                        <div class="border border-red-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-red-800 mb-3">🦠 4. Infections & Pleural Disorders</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Bacterial, viral, and fungal pneumonias</li>
                                    <li>Bronchiectasis with chronic airway infection</li>
                                    <li>Pleural effusions and pneumothorax</li>
                                    <li>ARDS and acute respiratory failure</li>
                                </ul>
                            </div>
                            <div class="text-xs text-red-600 bg-red-50 p-2 rounded">
                                <strong>Focus:</strong> Pathogen clearance, immune support, and pleural space management.
                            </div>
                        </div>
                    </div>

                    <div class="space-y-6">
                        <div class="border border-orange-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-orange-800 mb-3">🧫 5. Mycobacterial Diseases</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Latent and active tuberculosis</li>
                                    <li>Multidrug-resistant TB (MDR-TB)</li>
                                    <li>Non-tuberculous mycobacterial (NTM) infections</li>
                                    <li>Granulomatous immune responses</li>
                                </ul>
                            </div>
                            <div class="text-xs text-orange-600 bg-orange-50 p-2 rounded">
                                <strong>Focus:</strong> Immune surveillance, drug resistance monitoring, and granuloma stability.
                            </div>
                        </div>

                        <div class="border border-indigo-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-indigo-800 mb-3">🫀 6. Pulmonary Vascular Diseases</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Components:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Primary and secondary pulmonary hypertension</li>
                                    <li>Acute pulmonary embolism</li>
                                    <li>Chronic thromboembolic pulmonary hypertension (CTEPH)</li>
                                    <li>Cardiogenic and non-cardiogenic pulmonary edema</li>
                                </ul>
                            </div>
                            <div class="text-xs text-indigo-600 bg-indigo-50 p-2 rounded">
                                <strong>Focus:</strong> Vascular pressure management, clot resolution, and right heart protection.
                            </div>
                        </div>

                        <div class="border border-pink-200 rounded-lg p-4">
                            <h3 class="text-lg font-semibold text-pink-800 mb-3">😴 7. Sleep & Neurological Breathing Disorders</h3>
                            <div class="text-sm text-gray-700 mb-3">
                                <strong>Key Elements:</strong>
                                <ul class="list-disc list-inside mt-2 space-y-1">
                                    <li>Obstructive sleep apnea with airway collapse</li>
                                    <li>Central sleep apnea with brainstem dysfunction</li>
                                    <li>Mixed sleep apnea with combined mechanisms</li>
                                    <li>Sleep architecture and oxygenation patterns</li>
                                </ul>
                            </div>
                            <div class="text-xs text-pink-600 bg-pink-50 p-2 rounded">
                                <strong>Focus:</strong> Airway patency, respiratory drive, and sleep quality optimization.
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Protocol Cards Grid -->
        <div id="protocolGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Protocol cards will be dynamically generated here -->
        </div>

        <!-- Protocol Detail Modal -->
        <div id="protocolModal" class="fixed inset-0 bg-black bg-opacity-50 hidden z-50">
            <div class="flex items-center justify-center min-h-screen p-4">
                <div class="bg-white rounded-lg shadow-xl max-w-6xl w-full max-h-screen overflow-y-auto">
                    <div class="p-6 border-b border-gray-200">
                        <div class="flex justify-between items-start">
                            <div>
                                <h2 id="modalTitle" class="text-2xl font-bold text-gray-900"></h2>
                                <p id="modalCategory" class="text-sm text-gray-600 mt-1"></p>
                                <div id="modalDSM" class="text-xs text-sky-600 mt-1 font-medium"></div>
                            </div>
                            <button onclick="closeModal()" class="text-gray-400 hover:text-gray-600">
                                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                                </svg>
                            </button>
                        </div>
                    </div>
                    
                    <div class="p-6" id="modalContent">
                        <!-- Content will be dynamically populated -->
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Comprehensive respiratory and pulmonary disorders database
        const protocols = [
            // COPD (Chronic Obstructive Pulmonary Disease)
            {
                id: 1,
                name: "COPD - Emphysema",
                category: "copd",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Respiratory System / Alveolar Gas Exchange",
                regions: ["Alveoli", "Lung Parenchyma", "Respiratory Bronchioles", "Pulmonary Capillaries", "Diaphragm", "Intercostal Muscles"],
                neurotransmitters: ["Airflow Obstruction", "Gas Exchange Efficiency", "Lung Elasticity", "Alpha-1 Antitrypsin", "Inflammatory Markers (IL-8, TNF-α)", "Oxidative Stress"],
                dsm: "ICD-10: J43.9",
                description: "Protocol for emphysema targeting alveolar repair, gas exchange optimization, and respiratory muscle support.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Monitor oxygen saturation and respiratory rate. May improve gas exchange. Pulmonary rehabilitation essential. Avoid respiratory irritants. Oxygen therapy as needed."
            },
            {
                id: 2,
                name: "COPD - Chronic Bronchitis",
                category: "copd",
                severity: "moderate",
                duration: "40 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Bronchial System / Mucus Clearance",
                regions: ["Bronchi", "Bronchioles", "Mucus Glands", "Ciliary Epithelium", "Respiratory Muscles", "Airways"],
                neurotransmitters: ["Mucus Production", "Ciliary Function", "Airway Inflammation", "Bacterial Colonization", "Bronchial Hyperreactivity", "Cough Reflex"],
                dsm: "ICD-10: J44.1",
                description: "Protocol for chronic bronchitis targeting mucus clearance, airway inflammation reduction, and bronchial function improvement.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Monitor sputum production and color changes. May improve airway clearance. Smoking cessation critical. Bronchodilators and mucolytics as prescribed."
            },

            // Asthma (Adult)
            {
                id: 3,
                name: "Adult Asthma - Allergic",
                category: "asthma",
                severity: "moderate",
                duration: "35 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Bronchial System / Immune System",
                regions: ["Bronchi", "Bronchioles", "Mast Cells", "Smooth Muscle", "Mucus Glands", "Eosinophils"],
                neurotransmitters: ["IgE Response", "Histamine Release", "Leukotriene Production", "Bronchial Hyperreactivity", "Airway Inflammation", "Mucus Hypersecretion"],
                dsm: "ICD-10: J45.0",
                description: "Protocol for allergic asthma targeting bronchodilation, immune modulation, and trigger sensitivity reduction.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Monitor peak flow and symptoms. May reduce bronchial reactivity. Identify and avoid triggers. Keep rescue inhaler available. Allergy testing recommended."
            },
            {
                id: 4,
                name: "Adult Asthma - Non-Allergic",
                category: "asthma",
                severity: "moderate",
                duration: "35 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Bronchial System / Neurogenic Pathways",
                regions: ["Bronchi", "Bronchioles", "Vagal Pathways", "Smooth Muscle", "Respiratory Epithelium", "Autonomic Nerves"],
                neurotransmitters: ["Vagal Tone", "Acetylcholine Response", "Neurogenic Inflammation", "Bronchial Reactivity", "Epithelial Integrity", "Autonomic Balance"],
                dsm: "ICD-10: J45.1",
                description: "Protocol for non-allergic asthma targeting neurogenic pathways, autonomic balance, and bronchial stability.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Monitor triggers like stress, weather, exercise. May improve bronchial stability. Stress management important. Avoid irritants and pollutants."
            },
            {
                id: 5,
                name: "Exercise-Induced Asthma",
                category: "asthma",
                severity: "mild",
                duration: "30 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Bronchial System / Exercise Physiology",
                regions: ["Bronchi", "Bronchioles", "Respiratory Muscles", "Airway Epithelium", "Heat Exchange", "Moisture Loss"],
                neurotransmitters: ["Exercise Tolerance", "Airway Cooling", "Osmotic Changes", "Bronchial Protection", "Recovery Time", "Conditioning Response"],
                dsm: "ICD-10: J45.990",
                description: "Protocol for exercise-induced bronchoconstriction targeting airway protection during physical activity.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz"],
                notes: "Pre-exercise warm-up essential. May improve exercise tolerance. Use bronchodilator before activity. Monitor symptoms during exercise."
            },
            {
                id: 6,
                name: "Occupational Asthma",
                category: "asthma",
                severity: "moderate",
                duration: "40 minutes",
                ageGroup: "Adults 25+",
                primarySystems: "Bronchial System / Occupational Exposure",
                regions: ["Bronchi", "Bronchioles", "Respiratory Epithelium", "Immune Cells", "Mucus Glands", "Alveolar Macrophages"],
                neurotransmitters: ["Occupational Sensitizers", "Inflammatory Response", "Epithelial Damage", "Immune Sensitization", "Airway Remodeling", "Exposure History"],
                dsm: "ICD-10: J45.8",
                description: "Protocol for occupational asthma targeting workplace exposure effects and respiratory protection.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Identify workplace triggers. May support respiratory recovery. Workplace modifications essential. Consider job change if severe. Use protective equipment."
            },

            // Pulmonary Fibrosis
            {
                id: 7,
                name: "Idiopathic Pulmonary Fibrosis (IPF)",
                category: "fibrosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 60+",
                primarySystems: "Interstitial Lung / Alveolar Structure",
                regions: ["Alveolar Walls", "Interstitium", "Fibroblasts", "Collagen Matrix", "Pulmonary Capillaries", "Pleura"],
                neurotransmitters: ["Fibrotic Progression", "Collagen Deposition", "TGF-β Activity", "Lung Compliance", "Gas Diffusion", "Epithelial Repair"],
                dsm: "ICD-10: J84.112",
                description: "Protocol for IPF targeting fibrosis progression control, gas exchange optimization, and lung function preservation.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "PROGRESSIVE DISEASE. Monitor oxygen levels and exercise tolerance. May slow progression. Antifibrotic medications essential. Lung transplant evaluation may be needed."
            },
            {
                id: 8,
                name: "Secondary Pulmonary Fibrosis",
                category: "fibrosis",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Interstitial Lung / Inflammatory Response",
                regions: ["Alveolar Walls", "Interstitium", "Inflammatory Cells", "Fibroblasts", "Basement Membrane", "Lung Architecture"],
                neurotransmitters: ["Underlying Cause", "Inflammatory Response", "Fibrotic Markers", "Tissue Repair", "Immune Modulation", "Scarring Prevention"],
                dsm: "ICD-10: J84.10",
                description: "Protocol for secondary pulmonary fibrosis targeting underlying cause treatment and fibrosis limitation.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Identify and treat underlying cause. May limit progression. Avoid lung irritants. Immunosuppressive therapy often needed."
            },

            // Pneumonia (Bacterial / Viral / Fungal)
            {
                id: 9,
                name: "Bacterial Pneumonia",
                category: "pneumonia",
                severity: "severe",
                duration: "40 minutes",
                ageGroup: "All ages",
                primarySystems: "Alveolar System / Immune Response",
                regions: ["Alveoli", "Lung Parenchyma", "Neutrophils", "Macrophages", "Pulmonary Capillaries", "Pleural Space"],
                neurotransmitters: ["Bacterial Load", "Immune Response", "Inflammatory Markers", "Oxygenation", "Consolidation", "Antibiotic Sensitivity"],
                dsm: "ICD-10: J15.9",
                description: "Protocol for bacterial pneumonia supporting immune response, oxygenation, and recovery alongside antibiotic therapy.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "REQUIRES ANTIBIOTIC THERAPY. Monitor vital signs and oxygen saturation. May support immune response. Hospitalization may be needed for severe cases."
            },
            {
                id: 10,
                name: "Viral Pneumonia",
                category: "pneumonia",
                severity: "moderate",
                duration: "35 minutes",
                ageGroup: "All ages",
                primarySystems: "Alveolar System / Antiviral Immunity",
                regions: ["Alveoli", "Respiratory Epithelium", "T-Lymphocytes", "Interferon Response", "Lung Parenchyma", "Viral Replication Sites"],
                neurotransmitters: ["Viral Load", "Interferon Response", "T-Cell Activity", "Epithelial Repair", "Inflammatory Balance", "Recovery Markers"],
                dsm: "ICD-10: J12.9",
                description: "Protocol for viral pneumonia supporting antiviral immunity, epithelial repair, and symptom management.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Supportive care primary treatment. Monitor for bacterial superinfection. May support immune response. Rest and hydration essential."
            },
            {
                id: 11,
                name: "Fungal Pneumonia",
                category: "pneumonia",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Alveolar System / Antifungal Immunity",
                regions: ["Alveoli", "Lung Parenchyma", "Macrophages", "Neutrophils", "Fungal Spores", "Granulomas"],
                neurotransmitters: ["Fungal Burden", "Macrophage Function", "Granuloma Formation", "Antifungal Response", "Tissue Damage", "Immune Status"],
                dsm: "ICD-10: J17.2",
                description: "Protocol for fungal pneumonia supporting antifungal immunity and tissue protection alongside antifungal therapy.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "REQUIRES ANTIFUNGAL THERAPY. Often occurs in immunocompromised patients. May support immune response. Prolonged treatment usually needed."
            },
            {
                id: 12,
                name: "Aspiration Pneumonia",
                category: "pneumonia",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Alveolar System / Aspiration Response",
                regions: ["Lower Lobes", "Alveoli", "Bronchi", "Inflammatory Cells", "Gastric Contents", "Lung Parenchyma"],
                neurotransmitters: ["Aspiration Material", "Chemical Pneumonitis", "Secondary Infection", "Inflammatory Response", "Tissue Damage", "Airway Protection"],
                dsm: "ICD-10: J69.0",
                description: "Protocol for aspiration pneumonia targeting chemical injury response and secondary infection prevention.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "MEDICAL EMERGENCY. Requires immediate treatment. May support lung healing. Prevent future aspiration. Swallowing evaluation needed."
            },

            // Tuberculosis (Latent / Active / MDR)
            {
                id: 13,
                name: "Tuberculosis (Latent)",
                category: "tuberculosis",
                severity: "mild",
                duration: "40 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Pulmonary System / Immune Surveillance",
                regions: ["Lung Apices", "Granulomas", "T-Lymphocytes", "Macrophages", "Lymph Nodes", "Dormant Bacteria"],
                neurotransmitters: ["Immune Surveillance", "Granuloma Stability", "T-Cell Memory", "Bacterial Dormancy", "Reactivation Risk", "Immune Status"],
                dsm: "ICD-10: Z87.891",
                description: "Protocol for latent TB supporting immune surveillance and preventing reactivation.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Monitor for reactivation signs. May support immune surveillance. Treatment prevents active disease. Regular screening important."
            },
            {
                id: 14,
                name: "Tuberculosis (Active)",
                category: "tuberculosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Pulmonary System / Immune Response",
                regions: ["Lung Parenchyma", "Cavities", "Granulomas", "Lymph Nodes", "Pleura", "Bronchi"],
                neurotransmitters: ["Mycobacterial Load", "Granuloma Formation", "Cavitation", "Immune Response", "Tissue Damage", "Drug Resistance"],
                dsm: "ICD-10: A15.0",
                description: "Critical protocol for active TB supporting immune response and tissue healing alongside anti-TB therapy.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "REQUIRES ANTI-TB THERAPY. Highly contagious - isolation needed. May support immune response. Treatment duration 6-9 months minimum."
            },
            {
                id: 15,
                name: "Multidrug-Resistant TB (MDR-TB)",
                category: "tuberculosis",
                severity: "severe",
                duration: "55 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Pulmonary System / Drug-Resistant Pathogens",
                regions: ["Lung Parenchyma", "Cavitary Lesions", "Granulomas", "Lymph Nodes", "Pleura", "Bronchi", "Drug-Resistant Bacteria"],
                neurotransmitters: ["Drug Resistance Genes", "Mycobacterial Persistence", "Immune Exhaustion", "Inflammatory Markers", "Tissue Necrosis", "Treatment Response", "Bacterial Mutation"],
                dsm: "ICD-10: A15.0 (with resistance notation)",
                description: "Specialized protocol for MDR-TB targeting drug-resistant mycobacteria, immune system support, and treatment optimization.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz", "2127 Hz"],
                notes: "EXTREMELY SERIOUS CONDITION. Requires specialized anti-TB regimen 18-24 months. Strict isolation protocols. May support immune function against resistant strains. Close monitoring essential."
            },

            // Pulmonary Hypertension
            {
                id: 16,
                name: "Primary Pulmonary Hypertension",
                category: "pulmonary-hypertension",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Pulmonary Vascular / Right Heart",
                regions: ["Pulmonary Arteries", "Right Ventricle", "Right Atrium", "Pulmonary Capillaries", "Tricuspid Valve", "Pulmonary Valve"],
                neurotransmitters: ["Pulmonary Pressures", "Vascular Resistance", "Right Heart Function", "Endothelial Function", "Nitric Oxide", "Prostacyclin"],
                dsm: "ICD-10: I27.0",
                description: "Protocol for primary pulmonary hypertension targeting pressure reduction and right heart protection.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "LIFE-THREATENING CONDITION. Monitor exercise tolerance and symptoms. May support pulmonary circulation. Specialized medications essential."
            },
            {
                id: 17,
                name: "Secondary Pulmonary Hypertension",
                category: "pulmonary-hypertension",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Pulmonary Vascular / Underlying Disease",
                regions: ["Pulmonary Vessels", "Right Heart", "Underlying Pathology", "Gas Exchange", "Hypoxic Areas", "Vascular Remodeling"],
                neurotransmitters: ["Underlying Disease", "Hypoxic Vasoconstriction", "Vascular Remodeling", "Right Heart Strain", "Oxygenation", "Hemodynamics"],
                dsm: "ICD-10: I27.2",
                description: "Protocol for secondary pulmonary hypertension targeting underlying cause and hemodynamic support.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Treat underlying condition. Monitor right heart function. May support pulmonary circulation. Oxygen therapy often needed."
            },

            // Sleep Apnea (Obstructive / Central)
            {
                id: 18,
                name: "Sleep Apnea (Obstructive)",
                category: "sleep-apnea",
                severity: "moderate",
                duration: "35 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Upper Airway / Sleep Architecture",
                regions: ["Pharynx", "Soft Palate", "Tongue", "Upper Airway Muscles", "Respiratory Centers", "Sleep Centers"],
                neurotransmitters: ["Airway Patency", "Muscle Tone", "Arousal Threshold", "Oxygen Saturation", "Sleep Quality", "Autonomic Balance"],
                dsm: "ICD-10: G47.33",
                description: "Protocol for obstructive sleep apnea targeting airway patency, muscle tone, and sleep quality improvement.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "CPAP therapy often needed. Monitor sleep quality and daytime symptoms. May improve airway function. Weight loss beneficial."
            },
            {
                id: 19,
                name: "Sleep Apnea (Central)",
                category: "sleep-apnea",
                severity: "severe",
                duration: "40 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Respiratory Control / Neurological",
                regions: ["Medullary Respiratory Centers", "Chemoreceptors", "Respiratory Muscles", "Brainstem", "CO2 Sensitivity", "Respiratory Drive"],
                neurotransmitters: ["Respiratory Drive", "CO2 Sensitivity", "Chemoreceptor Function", "Neural Control", "Breathing Stability", "Sleep Architecture"],
                dsm: "ICD-10: G47.31",
                description: "Protocol for central sleep apnea targeting respiratory control centers and breathing stability.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Often associated with heart failure or neurological conditions. May support respiratory control. Specialized ventilation may be needed."
            },
            {
                id: 20,
                name: "Mixed Sleep Apnea",
                category: "sleep-apnea",
                severity: "severe",
                duration: "40 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Upper Airway / Respiratory Control",
                regions: ["Upper Airway", "Respiratory Centers", "Airway Muscles", "Chemoreceptors", "Sleep Centers", "Autonomic System"],
                neurotransmitters: ["Combined Mechanisms", "Airway Stability", "Respiratory Drive", "Sleep Fragmentation", "Oxygenation", "Arousal Response"],
                dsm: "ICD-10: G47.37",
                description: "Protocol for mixed sleep apnea addressing both obstructive and central components.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Complex condition requiring specialized treatment. May support both airway and respiratory control. Advanced ventilation often needed."
            },

            // Additional Respiratory Conditions
            {
                id: 21,
                name: "Acute Respiratory Distress Syndrome (ARDS)",
                category: "pneumonia",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Alveolar-Capillary Membrane / Gas Exchange",
                regions: ["Alveolar-Capillary Membrane", "Surfactant System", "Pulmonary Edema", "Inflammatory Cells", "Gas Exchange", "Lung Compliance"],
                neurotransmitters: ["Membrane Permeability", "Surfactant Function", "Inflammatory Response", "Oxygenation", "Lung Injury", "Recovery Factors"],
                dsm: "ICD-10: J80",
                description: "Critical supportive protocol for ARDS targeting membrane repair and gas exchange optimization.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "LIFE-THREATENING EMERGENCY. Requires intensive care. May support lung healing. Mechanical ventilation usually needed."
            },

            // Interstitial Lung Diseases (ILD)
            {
                id: 22,
                name: "Sarcoidosis (Pulmonary)",
                category: "fibrosis",
                severity: "moderate",
                duration: "45 minutes",
                ageGroup: "Adults 20-40",
                primarySystems: "Interstitial Lung / Immune System",
                regions: ["Hilar Lymph Nodes", "Lung Interstitium", "Granulomas", "T-Lymphocytes", "Alveolar Macrophages", "Pulmonary Vessels"],
                neurotransmitters: ["ACE Levels", "Granuloma Formation", "T-Cell Activity", "IL-2", "TNF-α", "Calcium Metabolism", "Immune Dysregulation"],
                dsm: "ICD-10: D86.0",
                description: "Protocol for pulmonary sarcoidosis targeting granulomatous inflammation and immune system modulation.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Multi-system disease. Monitor ACE levels and calcium. May improve immune balance. Corticosteroids often needed. Can resolve spontaneously."
            },
            {
                id: 23,
                name: "Hypersensitivity Pneumonitis",
                category: "fibrosis",
                severity: "moderate",
                duration: "40 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Alveolar System / Immune Hypersensitivity",
                regions: ["Alveoli", "Interstitium", "Bronchioles", "Immune Complexes", "Inflammatory Cells", "Lung Parenchyma"],
                neurotransmitters: ["Antigen Exposure", "Immune Complex Formation", "T-Cell Response", "Inflammatory Mediators", "Fibrotic Markers", "Sensitization Patterns"],
                dsm: "ICD-10: J67.9",
                description: "Protocol for hypersensitivity pneumonitis targeting antigen response and inflammatory control.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Identify and avoid causative antigen. May support immune modulation. Farmer's lung, bird fancier's lung common forms. Antigen avoidance essential."
            },
            {
                id: 24,
                name: "Pneumoconiosis (Asbestosis)",
                category: "fibrosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Interstitial Lung / Occupational Exposure",
                regions: ["Lower Lobes", "Pleura", "Asbestos Fibers", "Fibroblasts", "Alveolar Macrophages", "Lung Parenchyma"],
                neurotransmitters: ["Asbestos Fiber Load", "Fibrotic Progression", "Pleural Plaques", "Inflammatory Response", "Oxidative Stress", "Mesothelioma Risk"],
                dsm: "ICD-10: J61",
                description: "Protocol for asbestosis targeting fiber-induced inflammation and fibrosis progression control.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "PROGRESSIVE DISEASE. High cancer risk. May slow progression. No cure available. Regular cancer screening essential. Avoid further exposure."
            },
            {
                id: 25,
                name: "Pneumoconiosis (Silicosis)",
                category: "fibrosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Interstitial Lung / Silica Exposure",
                regions: ["Upper Lobes", "Hilar Lymph Nodes", "Silica Particles", "Macrophages", "Fibrotic Nodules", "Lung Architecture"],
                neurotransmitters: ["Silica Particle Load", "Macrophage Activation", "Fibrotic Nodules", "Progressive Massive Fibrosis", "Autoimmune Markers", "Lung Function"],
                dsm: "ICD-10: J62.8",
                description: "Protocol for silicosis targeting silica-induced lung damage and progressive fibrosis control.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "PROGRESSIVE DISEASE. Increased TB and autoimmune disease risk. May slow progression. Avoid further silica exposure. Regular monitoring essential."
            },

            // Pulmonary Embolism
            {
                id: 26,
                name: "Acute Pulmonary Embolism",
                category: "pulmonary-hypertension",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Pulmonary Vascular / Thrombotic",
                regions: ["Pulmonary Arteries", "Blood Clots", "Right Heart", "Lung Perfusion", "Coagulation System", "Venous System"],
                neurotransmitters: ["Clot Burden", "D-Dimer", "Fibrin Formation", "Platelet Activation", "Endothelial Damage", "Hypoxemia", "Right Heart Strain"],
                dsm: "ICD-10: I26.9",
                description: "Critical protocol for acute PE supporting circulation and oxygenation alongside anticoagulation therapy.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "MEDICAL EMERGENCY. Requires immediate anticoagulation. May support circulation. High mortality risk. Thrombolytic therapy may be needed."
            },
            {
                id: 27,
                name: "Chronic Thromboembolic Pulmonary Hypertension (CTEPH)",
                category: "pulmonary-hypertension",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Pulmonary Vascular / Chronic Obstruction",
                regions: ["Pulmonary Arteries", "Organized Thrombi", "Right Heart", "Pulmonary Circulation", "Vascular Remodeling", "Exercise Capacity"],
                neurotransmitters: ["Chronic Obstruction", "Pulmonary Pressures", "Vascular Remodeling", "Right Heart Function", "Exercise Tolerance", "Anticoagulation Status"],
                dsm: "ICD-10: I27.24",
                description: "Protocol for CTEPH targeting chronic obstruction and pulmonary hypertension management.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "Potentially curable with surgery. May support circulation. Lifelong anticoagulation needed. Pulmonary endarterectomy may be curative."
            },

            // Pleural Disorders
            {
                id: 28,
                name: "Pleural Effusion (Exudative)",
                category: "pneumonia",
                severity: "moderate",
                duration: "40 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Pleural Space / Inflammatory",
                regions: ["Pleural Space", "Pleural Membranes", "Inflammatory Cells", "Protein Accumulation", "Lung Compression", "Lymphatic Drainage"],
                neurotransmitters: ["Protein Content", "LDH Levels", "Inflammatory Markers", "Pleural Fluid", "Underlying Pathology", "Respiratory Mechanics"],
                dsm: "ICD-10: J94.8",
                description: "Protocol for exudative pleural effusion targeting inflammation and fluid reabsorption.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "Identify underlying cause. May support fluid reabsorption. Thoracentesis may be needed. Monitor for reaccumulation."
            },
            {
                id: 35,
                name: "Pleural Effusion (Transudative)",
                category: "pneumonia",
                severity: "moderate",
                duration: "35 minutes",
                ageGroup: "Adults 40+",
                primarySystems: "Pleural Space / Hydrostatic Pressure",
                regions: ["Pleural Space", "Pleural Capillaries", "Hydrostatic Pressure", "Oncotic Pressure", "Fluid Balance", "Cardiac Function"],
                neurotransmitters: ["Hydrostatic Pressure", "Protein Levels", "Cardiac Output", "Fluid Balance", "Oncotic Pressure", "Systemic Circulation"],
                dsm: "ICD-10: J94.8",
                description: "Protocol for transudative pleural effusion targeting pressure balance and cardiac function.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz"],
                notes: "Treat underlying heart/liver/kidney disease. May support fluid balance. Usually bilateral. Thoracentesis rarely needed."
            },
            {
                id: 29,
                name: "Pneumothorax (Spontaneous)",
                category: "pneumonia",
                severity: "severe",
                duration: "35 minutes",
                ageGroup: "Adults 20+",
                primarySystems: "Pleural Space / Air Leak",
                regions: ["Pleural Space", "Lung Surface", "Air Leak", "Chest Wall", "Respiratory Mechanics", "Lung Re-expansion"],
                neurotransmitters: ["Air Leak Size", "Lung Collapse", "Pleural Pressure", "Respiratory Distress", "Healing Response", "Recurrence Risk"],
                dsm: "ICD-10: J93.1",
                description: "Protocol for spontaneous pneumothorax supporting lung re-expansion and healing.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz"],
                notes: "MEDICAL EMERGENCY if large. May support healing. Chest tube may be needed. High recurrence risk in young tall males."
            },
            {
                id: 36,
                name: "Pneumothorax (Traumatic)",
                category: "pneumonia",
                severity: "severe",
                duration: "40 minutes",
                ageGroup: "All ages",
                primarySystems: "Pleural Space / Trauma Response",
                regions: ["Pleural Space", "Chest Wall Injury", "Lung Laceration", "Rib Fractures", "Trauma Site", "Emergency Response"],
                neurotransmitters: ["Trauma Severity", "Air Leak Volume", "Hemodynamic Stability", "Pain Response", "Tissue Damage", "Emergency Stabilization"],
                dsm: "ICD-10: S27.0",
                description: "Critical protocol for traumatic pneumothorax supporting emergency stabilization and healing.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz"],
                notes: "TRAUMA EMERGENCY. Requires immediate chest tube. May support healing. Monitor for hemothorax. Surgical intervention may be needed."
            },
            {
                id: 37,
                name: "Tension Pneumothorax",
                category: "pneumonia",
                severity: "severe",
                duration: "30 minutes",
                ageGroup: "All ages",
                primarySystems: "Pleural Space / Cardiovascular Emergency",
                regions: ["Pleural Space", "Mediastinum", "Venous Return", "Cardiac Output", "Respiratory Failure", "Hemodynamic Collapse"],
                neurotransmitters: ["Mediastinal Shift", "Venous Return", "Cardiac Preload", "Respiratory Failure", "Hemodynamic Collapse", "Emergency Decompression"],
                dsm: "ICD-10: J93.0",
                description: "LIFE-THREATENING emergency protocol supporting immediate decompression and cardiovascular stability.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "IMMEDIATE LIFE-THREATENING EMERGENCY. Requires needle decompression NOW. May support stabilization. Death within minutes without treatment."
            },
            {
                id: 38,
                name: "Hemothorax",
                category: "pneumonia",
                severity: "severe",
                duration: "45 minutes",
                ageGroup: "All ages",
                primarySystems: "Pleural Space / Hemorrhage Control",
                regions: ["Pleural Space", "Blood Accumulation", "Intercostal Vessels", "Lung Surface", "Chest Wall", "Hemodynamic Status"],
                neurotransmitters: ["Blood Volume", "Hemodynamic Stability", "Coagulation Status", "Respiratory Compromise", "Shock Risk", "Surgical Intervention"],
                dsm: "ICD-10: J94.2",
                description: "Critical protocol for hemothorax supporting hemostasis and respiratory function.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "MEDICAL EMERGENCY. Requires chest tube drainage. May support hemostasis. Monitor for shock. Surgical exploration may be needed."
            },

            // Lung Infections (Non-TB)
            {
                id: 30,
                name: "Bronchiectasis (Post-Infectious)",
                category: "pneumonia",
                severity: "moderate",
                duration: "45 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Bronchial System / Chronic Infection",
                regions: ["Dilated Bronchi", "Airway Walls", "Chronic Infection", "Mucus Plugs", "Inflammatory Cells", "Respiratory Muscles"],
                neurotransmitters: ["Airway Dilation", "Chronic Infection", "Mucus Clearance", "Inflammatory Response", "Bacterial Colonization", "Lung Function"],
                dsm: "ICD-10: J47.9",
                description: "Protocol for post-infectious bronchiectasis targeting airway clearance and infection control.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Chronic condition requiring ongoing management. May improve airway clearance. Airway clearance techniques essential. Antibiotics for exacerbations."
            },
            {
                id: 39,
                name: "Bronchiectasis (Congenital)",
                category: "pneumonia",
                severity: "moderate",
                duration: "50 minutes",
                ageGroup: "All ages",
                primarySystems: "Bronchial System / Genetic Defects",
                regions: ["Congenitally Dilated Bronchi", "Ciliary Dysfunction", "Mucus Transport", "Genetic Defects", "Immune Deficiency", "Airway Development"],
                neurotransmitters: ["Genetic Factors", "Ciliary Function", "Immune Deficiency", "Mucus Properties", "Airway Development", "Infection Susceptibility"],
                dsm: "ICD-10: Q33.4",
                description: "Protocol for congenital bronchiectasis targeting genetic factors and immune support.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "Genetic condition present from birth. May support immune function. Requires lifelong management. Consider genetic counseling."
            },
            {
                id: 40,
                name: "Fungal Lung Abscesses",
                category: "pneumonia",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Pulmonary System / Fungal Infection",
                regions: ["Lung Abscesses", "Necrotic Tissue", "Fungal Hyphae", "Immune Response", "Cavitary Lesions", "Surrounding Lung"],
                neurotransmitters: ["Fungal Load", "Tissue Necrosis", "Immune Response", "Abscess Formation", "Antifungal Resistance", "Systemic Spread"],
                dsm: "ICD-10: J85.0",
                description: "Critical protocol for fungal lung abscesses supporting immune response and tissue healing.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "SERIOUS INFECTION. Requires antifungal therapy. May support immune response. Often in immunocompromised patients. Surgical drainage may be needed."
            },
            {
                id: 31,
                name: "Non-Tuberculous Mycobacterial (NTM) Lung Disease",
                category: "tuberculosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Pulmonary System / Atypical Mycobacteria",
                regions: ["Lung Parenchyma", "Bronchi", "Cavities", "Immune Cells", "Lymph Nodes", "Atypical Mycobacteria"],
                neurotransmitters: ["NTM Species", "Immune Response", "Cavitation", "Inflammatory Markers", "Treatment Response", "Disease Progression"],
                dsm: "ICD-10: A31.0",
                description: "Protocol for NTM lung disease supporting immune response and treatment effectiveness.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "Difficult to treat. May support immune response. Prolonged multi-drug therapy needed. Often affects immunocompromised patients."
            },

            // Other Pulmonary Disorders
            {
                id: 32,
                name: "Alpha-1 Antitrypsin Deficiency",
                category: "copd",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Genetic / Protease-Antiprotease Balance",
                regions: ["Alveoli", "Liver", "Alpha-1 Antitrypsin", "Elastin Fibers", "Protease Activity", "Lung Parenchyma"],
                neurotransmitters: ["Alpha-1 Antitrypsin Levels", "Protease Activity", "Elastin Degradation", "Genetic Markers", "Liver Function", "Lung Protection"],
                dsm: "ICD-10: E88.01",
                description: "Protocol for Alpha-1 deficiency targeting protease balance and lung protection.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "Genetic condition. May support lung protection. Alpha-1 replacement therapy available. Avoid smoking absolutely. Liver involvement possible."
            },
            {
                id: 33,
                name: "Pulmonary Edema (Cardiogenic)",
                category: "pulmonary-hypertension",
                severity: "severe",
                duration: "40 minutes",
                ageGroup: "Adults 50+",
                primarySystems: "Pulmonary Vascular / Cardiac",
                regions: ["Alveoli", "Pulmonary Capillaries", "Left Heart", "Fluid Accumulation", "Gas Exchange", "Pulmonary Circulation"],
                neurotransmitters: ["Left Heart Function", "Pulmonary Pressures", "Fluid Balance", "BNP Levels", "Oxygenation", "Cardiac Output"],
                dsm: "ICD-10: J81.0",
                description: "Critical protocol for cardiogenic pulmonary edema supporting cardiac function and fluid clearance.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "MEDICAL EMERGENCY. Requires immediate cardiac treatment. May support fluid clearance. Diuretics and cardiac medications essential."
            },
            {
                id: 34,
                name: "Occupational Lung Disease (Chemical)",
                category: "fibrosis",
                severity: "moderate",
                duration: "45 minutes",
                ageGroup: "Adults 25+",
                primarySystems: "Respiratory System / Chemical Exposure",
                regions: ["Respiratory Epithelium", "Alveoli", "Chemical Irritants", "Inflammatory Response", "Airway Damage", "Lung Parenchyma"],
                neurotransmitters: ["Chemical Exposure", "Epithelial Damage", "Inflammatory Markers", "Oxidative Stress", "Repair Mechanisms", "Sensitization"],
                dsm: "ICD-10: J68.9",
                description: "Protocol for chemical lung injury targeting detoxification and respiratory healing.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz"],
                notes: "Remove from exposure immediately. May support detoxification. Identify causative agent. Workplace safety measures essential."
            },
            {
                id: 41,
                name: "Occupational Lung Disease (Dust Exposure)",
                category: "fibrosis",
                severity: "severe",
                duration: "50 minutes",
                ageGroup: "Adults 30+",
                primarySystems: "Respiratory System / Particle Inhalation",
                regions: ["Alveolar Macrophages", "Lung Parenchyma", "Dust Particles", "Fibrotic Response", "Lymph Nodes", "Pleural Space"],
                neurotransmitters: ["Dust Particle Load", "Macrophage Activation", "Fibrotic Progression", "Inflammatory Response", "Lung Function Decline", "Occupational History"],
                dsm: "ICD-10: J64",
                description: "Protocol for dust-induced lung disease targeting particle clearance and fibrosis prevention.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz"],
                notes: "PROGRESSIVE DISEASE. Remove from dust exposure. May slow progression. Regular monitoring essential. No cure available."
            },
            {
                id: 42,
                name: "Acute Respiratory Distress Syndrome (ARDS) - Non-Cardiogenic",
                category: "pneumonia",
                severity: "severe",
                duration: "55 minutes",
                ageGroup: "Adults 18+",
                primarySystems: "Alveolar-Capillary Membrane / Acute Lung Injury",
                regions: ["Alveolar-Capillary Membrane", "Surfactant System", "Pulmonary Edema", "Inflammatory Cells", "Gas Exchange", "Lung Compliance", "Hyaline Membranes"],
                neurotransmitters: ["Membrane Permeability", "Surfactant Function", "Inflammatory Cytokines", "Oxygenation Index", "Lung Injury Score", "Recovery Factors", "Ventilator Settings"],
                dsm: "ICD-10: J80",
                description: "Critical protocol for non-cardiogenic ARDS targeting membrane repair and gas exchange optimization.",
                frequencies: ["7.83 Hz", "10 Hz", "40 Hz", "304 Hz", "528 Hz", "727 Hz", "880 Hz", "1550 Hz", "2127 Hz"],
                notes: "LIFE-THREATENING EMERGENCY. Requires intensive care and mechanical ventilation. May support lung healing. High mortality risk. Prone positioning may help."
            }
        ];

        let filteredProtocols = [...protocols];

        // Helper functions for detailed protocol information
        function getRegionDetails(region) {
            const details = {
                'Alveoli': 'Tiny air sacs where oxygen and carbon dioxide exchange occurs',
                'Lung Parenchyma': 'Functional tissue of the lungs including alveoli and capillaries',
                'Respiratory Bronchioles': 'Small airways leading to alveolar sacs',
                'Pulmonary Capillaries': 'Tiny blood vessels surrounding alveoli for gas exchange',
                'Diaphragm': 'Primary breathing muscle separating chest and abdomen',
                'Intercostal Muscles': 'Muscles between ribs assisting with breathing',
                'Bronchi': 'Main airways branching from trachea to lungs',
                'Bronchioles': 'Smaller airways within the lungs',
                'Mucus Glands': 'Structures producing protective mucus in airways',
                'Ciliary Epithelium': 'Hair-like structures moving mucus and debris upward',
                'Respiratory Muscles': 'Muscles involved in breathing mechanics',
                'Airways': 'Passages carrying air to and from lungs',
                'Mast Cells': 'Immune cells releasing histamine and inflammatory mediators',
                'Smooth Muscle': 'Muscle in airway walls controlling diameter',
                'Eosinophils': 'White blood cells involved in allergic responses',
                'Vagal Pathways': 'Nerve pathways controlling airway constriction',
                'Respiratory Epithelium': 'Lining of respiratory tract',
                'Autonomic Nerves': 'Nerves controlling involuntary airway functions',
                'Heat Exchange': 'Process of warming and cooling inhaled air',
                'Moisture Loss': 'Water loss during breathing, especially during exercise',
                'Alveolar Walls': 'Thin barriers between air and blood in lungs',
                'Interstitium': 'Tissue space between alveoli and capillaries',
                'Fibroblasts': 'Cells producing collagen and scar tissue',
                'Collagen Matrix': 'Structural protein framework in lung tissue',
                'Pleura': 'Membrane lining lungs and chest cavity',
                'Inflammatory Cells': 'White blood cells responding to injury or infection',
                'Basement Membrane': 'Structural layer supporting epithelial cells',
                'Lung Architecture': 'Overall structural organization of lung tissue',
                'Neutrophils': 'White blood cells fighting bacterial infections',
                'Macrophages': 'Large immune cells engulfing pathogens and debris',
                'Pleural Space': 'Fluid-filled space between lung and chest wall',
                'T-Lymphocytes': 'Immune cells coordinating antiviral responses',
                'Interferon Response': 'Antiviral protein system',
                'Viral Replication Sites': 'Cellular locations where viruses multiply',
                'Fungal Spores': 'Reproductive units of fungi causing infection',
                'Granulomas': 'Collections of immune cells surrounding infections',
                'Lung Apices': 'Upper portions of lungs, common TB location',
                'Lymph Nodes': 'Immune system filtering stations',
                'Dormant Bacteria': 'Inactive bacterial forms in latent infection',
                'Cavities': 'Hollow spaces formed by tissue destruction',
                'Cavitary Lesions': 'Hollow areas in lung tissue from TB damage',
                'Drug-Resistant Bacteria': 'Bacteria that survive standard treatments',
                'Pulmonary Arteries': 'Blood vessels carrying blood from heart to lungs',
                'Right Ventricle': 'Heart chamber pumping blood to lungs',
                'Right Atrium': 'Heart chamber receiving blood from body',
                'Tricuspid Valve': 'Valve between right atrium and ventricle',
                'Pulmonary Valve': 'Valve between right ventricle and pulmonary artery',
                'Vascular Remodeling': 'Structural changes in blood vessel walls',
                'Hypoxic Areas': 'Regions with low oxygen levels',
                'Pharynx': 'Throat area behind mouth and nose',
                'Soft Palate': 'Soft tissue at back of roof of mouth',
                'Tongue': 'Muscular organ that can obstruct airway during sleep',
                'Upper Airway Muscles': 'Muscles maintaining airway patency',
                'Respiratory Centers': 'Brain areas controlling breathing',
                'Sleep Centers': 'Brain regions regulating sleep-wake cycles',
                'Medullary Respiratory Centers': 'Brainstem areas controlling breathing rhythm',
                'Chemoreceptors': 'Sensors detecting oxygen and carbon dioxide levels',
                'Brainstem': 'Lower brain area controlling vital functions',
                'CO2 Sensitivity': 'Ability to detect carbon dioxide levels',
                'Respiratory Drive': 'Neural impulse to breathe',
                'Alveolar-Capillary Membrane': 'Barrier between air and blood',
                'Surfactant System': 'Substance reducing surface tension in alveoli',
                'Pulmonary Edema': 'Fluid accumulation in lungs',
                'Lung Compliance': 'Ability of lungs to expand and contract',
                'Lower Lobes': 'Bottom portions of lungs commonly affected by aspiration',
                'Gastric Contents': 'Stomach contents that can be aspirated into lungs',
                'Hilar Lymph Nodes': 'Lymph nodes at the root of the lungs',
                'Lung Interstitium': 'Tissue framework between alveoli',
                'Alveolar Macrophages': 'Immune cells in air sacs',
                'Pulmonary Vessels': 'Blood vessels within the lungs',
                'Immune Complexes': 'Antibody-antigen combinations causing inflammation',
                'Asbestos Fibers': 'Microscopic mineral fibers causing lung disease',
                'Pleural Plaques': 'Calcified deposits on pleural surfaces',
                'Silica Particles': 'Crystalline dust particles causing silicosis',
                'Fibrotic Nodules': 'Scar tissue formations in lungs',
                'Blood Clots': 'Coagulated blood blocking vessels',
                'Lung Perfusion': 'Blood flow through lung tissue',
                'Coagulation System': 'Blood clotting mechanisms',
                'Venous System': 'Veins returning blood to heart',
                'Organized Thrombi': 'Old blood clots that have become fibrous',
                'Exercise Capacity': 'Ability to perform physical activity',
                'Pleural Membranes': 'Thin layers lining lungs and chest cavity',
                'Protein Accumulation': 'Excess protein in pleural fluid',
                'Lung Compression': 'Pressure on lung tissue from fluid',
                'Lymphatic Drainage': 'System removing excess fluid',
                'Lung Surface': 'Outer layer of lung tissue',
                'Air Leak': 'Escape of air from lung into pleural space',
                'Chest Wall': 'Rib cage and surrounding muscles',
                'Lung Re-expansion': 'Process of lung returning to normal size',
                'Dilated Bronchi': 'Abnormally widened airways',
                'Airway Walls': 'Structural boundaries of breathing passages',
                'Chronic Infection': 'Long-term bacterial colonization',
                'Mucus Plugs': 'Thick secretions blocking airways',
                'Atypical Mycobacteria': 'Non-TB mycobacterial species',
                'Liver': 'Organ affected in Alpha-1 antitrypsin deficiency',
                'Alpha-1 Antitrypsin': 'Enzyme protecting lungs from damage',
                'Elastin Fibers': 'Proteins providing lung elasticity',
                'Protease Activity': 'Enzyme activity breaking down proteins',
                'Left Heart': 'Left side of heart pumping to body',
                'Fluid Accumulation': 'Excess fluid in lung tissue',
                'Gas Exchange': 'Transfer of oxygen and carbon dioxide',
                'Pulmonary Circulation': 'Blood flow through lungs',
                'Chemical Irritants': 'Substances causing airway inflammation',
                'Airway Damage': 'Injury to breathing passages',
                'Pleural Capillaries': 'Small blood vessels in pleural membranes',
                'Hydrostatic Pressure': 'Fluid pressure in blood vessels',
                'Oncotic Pressure': 'Protein-related pressure drawing fluid',
                'Cardiac Function': 'Heart pumping performance',
                'Chest Wall Injury': 'Trauma to rib cage and surrounding structures',
                'Lung Laceration': 'Tear or cut in lung tissue',
                'Rib Fractures': 'Broken ribs from trauma',
                'Trauma Site': 'Location of injury',
                'Emergency Response': 'Immediate medical intervention',
                'Mediastinum': 'Central chest cavity containing heart',
                'Venous Return': 'Blood flow back to heart',
                'Hemodynamic Collapse': 'Cardiovascular system failure',
                'Blood Accumulation': 'Collection of blood in pleural space',
                'Intercostal Vessels': 'Blood vessels between ribs',
                'Hemodynamic Status': 'Cardiovascular stability',
                'Congenitally Dilated Bronchi': 'Airways widened from birth',
                'Ciliary Dysfunction': 'Impaired hair-like structure function',
                'Mucus Transport': 'Movement of secretions through airways',
                'Genetic Defects': 'Inherited abnormalities',
                'Immune Deficiency': 'Weakened immune system',
                'Airway Development': 'Formation and growth of breathing passages',
                'Lung Abscesses': 'Pus-filled cavities in lung tissue',
                'Necrotic Tissue': 'Dead tissue from infection',
                'Fungal Hyphae': 'Thread-like fungal structures',
                'Cavitary Lesions': 'Hollow spaces from tissue destruction',
                'Surrounding Lung': 'Healthy lung tissue around infection',
                'Dust Particles': 'Microscopic particles inhaled at work',
                'Fibrotic Response': 'Scar tissue formation reaction',
                'Hyaline Membranes': 'Protein deposits in damaged alveoli'
            };
            return details[region] || 'Respiratory structure and function';
        }

        function getNeurotransmitterDetails(nt) {
            const details = {
                'Airflow Obstruction': 'Reduced air movement through airways',
                'Gas Exchange Efficiency': 'Effectiveness of oxygen and CO2 transfer',
                'Lung Elasticity': 'Ability of lungs to return to original shape',
                'Alpha-1 Antitrypsin': 'Protein protecting lungs from enzyme damage',
                'Inflammatory Markers (IL-8, TNF-α)': 'Proteins indicating lung inflammation',
                'Oxidative Stress': 'Cellular damage from reactive oxygen species',
                'Mucus Production': 'Amount and consistency of airway secretions',
                'Ciliary Function': 'Movement of hair-like structures clearing mucus',
                'Airway Inflammation': 'Swelling and irritation of breathing passages',
                'Bacterial Colonization': 'Persistent bacterial presence in airways',
                'Bronchial Hyperreactivity': 'Excessive airway response to stimuli',
                'Cough Reflex': 'Protective mechanism clearing airways',
                'IgE Response': 'Allergic antibody reaction',
                'Histamine Release': 'Chemical causing allergic symptoms',
                'Leukotriene Production': 'Inflammatory molecules in asthma',
                'Mucus Hypersecretion': 'Excessive mucus production',
                'Vagal Tone': 'Nerve activity affecting airway constriction',
                'Acetylcholine Response': 'Neurotransmitter causing bronchoconstriction',
                'Neurogenic Inflammation': 'Nerve-mediated inflammatory response',
                'Epithelial Integrity': 'Health of airway lining',
                'Autonomic Balance': 'Balance between sympathetic and parasympathetic systems',
                'Exercise Tolerance': 'Ability to perform physical activity',
                'Airway Cooling': 'Temperature changes during exercise breathing',
                'Osmotic Changes': 'Fluid shifts affecting airway function',
                'Bronchial Protection': 'Mechanisms preventing exercise-induced symptoms',
                'Recovery Time': 'Duration to return to baseline after exercise',
                'Conditioning Response': 'Adaptive changes with regular exercise',
                'Occupational Sensitizers': 'Workplace substances causing asthma',
                'Exposure History': 'Record of workplace chemical contact',
                'Fibrotic Progression': 'Advancement of scar tissue formation',
                'Collagen Deposition': 'Accumulation of structural protein',
                'TGF-β Activity': 'Growth factor promoting fibrosis',
                'Lung Compliance': 'Lung flexibility and expandability',
                'Gas Diffusion': 'Movement of gases across lung membranes',
                'Epithelial Repair': 'Healing of damaged airway lining',
                'Underlying Cause': 'Root factor causing secondary condition',
                'Inflammatory Response': 'Immune system reaction to injury',
                'Fibrotic Markers': 'Indicators of scar tissue formation',
                'Tissue Repair': 'Process of healing damaged lung tissue',
                'Immune Modulation': 'Regulation of immune system activity',
                'Scarring Prevention': 'Measures to limit scar tissue formation',
                'Bacterial Load': 'Amount of bacteria present in infection',
                'Immune Response': 'Body\'s defense against pathogens',
                'Oxygenation': 'Process of oxygen delivery to tissues',
                'Consolidation': 'Lung tissue filled with inflammatory material',
                'Antibiotic Sensitivity': 'Bacterial response to antibiotic treatment',
                'Viral Load': 'Amount of virus present in infection',
                'Interferon Response': 'Antiviral protein production',
                'T-Cell Activity': 'Immune cell function against viruses',
                'Recovery Markers': 'Indicators of healing progress',
                'Fungal Burden': 'Amount of fungal organisms present',
                'Macrophage Function': 'Large immune cell activity',
                'Granuloma Formation': 'Immune cell clustering around infection',
                'Antifungal Response': 'Body\'s defense against fungal infection',
                'Tissue Damage': 'Injury to lung structures',
                'Immune Status': 'Overall immune system function',
                'Aspiration Material': 'Foreign substances inhaled into lungs',
                'Chemical Pneumonitis': 'Lung inflammation from chemical irritation',
                'Secondary Infection': 'Bacterial infection following aspiration',
                'Airway Protection': 'Mechanisms preventing aspiration',
                'Immune Surveillance': 'Ongoing immune monitoring for threats',
                'Granuloma Stability': 'Maintenance of immune cell clusters',
                'T-Cell Memory': 'Immune system memory of past infections',
                'Bacterial Dormancy': 'Inactive state of bacteria',
                'Reactivation Risk': 'Probability of latent infection becoming active',
                'Mycobacterial Load': 'Amount of TB bacteria present',
                'Cavitation': 'Formation of hollow spaces in lung tissue',
                'Drug Resistance': 'Bacterial resistance to medications',
                'Drug Resistance Genes': 'Genetic factors enabling antibiotic resistance',
                'Mycobacterial Persistence': 'Ability of TB bacteria to survive treatment',
                'Immune Exhaustion': 'Weakened immune response from chronic infection',
                'Tissue Necrosis': 'Death of lung tissue',
                'Treatment Response': 'Patient reaction to anti-TB therapy',
                'Bacterial Mutation': 'Genetic changes in bacteria enabling resistance',
                'Pulmonary Pressures': 'Blood pressure in lung circulation',
                'Vascular Resistance': 'Opposition to blood flow in lung vessels',
                'Right Heart Function': 'Pumping ability of right side of heart',
                'Endothelial Function': 'Health of blood vessel lining',
                'Nitric Oxide': 'Molecule causing blood vessel dilation',
                'Prostacyclin': 'Substance preventing blood clots and dilating vessels',
                'Underlying Disease': 'Primary condition causing secondary problems',
                'Hypoxic Vasoconstriction': 'Blood vessel narrowing due to low oxygen',
                'Right Heart Strain': 'Stress on right side of heart',
                'Hemodynamics': 'Blood flow and pressure dynamics',
                'Airway Patency': 'Openness of breathing passages',
                'Muscle Tone': 'Tension in airway muscles',
                'Arousal Threshold': 'Level of stimulation needed to wake up',
                'Oxygen Saturation': 'Percentage of oxygen in blood',
                'Sleep Quality': 'Restfulness and efficiency of sleep',
                'Respiratory Drive': 'Neural impulse to breathe',
                'CO2 Sensitivity': 'Ability to detect carbon dioxide levels',
                'Chemoreceptor Function': 'Sensor activity for blood gases',
                'Neural Control': 'Nervous system regulation of breathing',
                'Breathing Stability': 'Consistent respiratory pattern',
                'Sleep Architecture': 'Structure and stages of sleep',
                'Combined Mechanisms': 'Multiple factors causing sleep apnea',
                'Airway Stability': 'Maintenance of open breathing passages',
                'Sleep Fragmentation': 'Disrupted sleep continuity',
                'Arousal Response': 'Awakening reaction to breathing problems',
                'Membrane Permeability': 'Barrier function between air and blood',
                'Surfactant Function': 'Surface tension reduction in alveoli',
                'Lung Injury': 'Damage to lung tissue and function',
                'Recovery Factors': 'Elements promoting healing',
                'ACE Levels': 'Angiotensin-converting enzyme concentration',
                'T-Cell Activity': 'Immune cell function',
                'IL-2': 'Interleukin-2 immune signaling molecule',
                'TNF-α': 'Tumor necrosis factor-alpha inflammatory marker',
                'Calcium Metabolism': 'Processing of calcium in the body',
                'Immune Dysregulation': 'Abnormal immune system function',
                'Antigen Exposure': 'Contact with allergenic substances',
                'Immune Complex Formation': 'Antibody-antigen binding',
                'T-Cell Response': 'Immune cell reaction to antigens',
                'Inflammatory Mediators': 'Molecules promoting inflammation',
                'Sensitization Patterns': 'Development of allergic responses',
                'Asbestos Fiber Load': 'Amount of asbestos in lung tissue',
                'Pleural Plaques': 'Calcified deposits on lung lining',
                'Mesothelioma Risk': 'Probability of developing lung cancer',
                'Silica Particle Load': 'Amount of silica dust in lungs',
                'Macrophage Activation': 'Immune cell response to particles',
                'Fibrotic Nodules': 'Scar tissue formations',
                'Progressive Massive Fibrosis': 'Advanced scarring pattern',
                'Autoimmune Markers': 'Indicators of self-attacking immunity',
                'Lung Function': 'Overall respiratory performance',
                'Clot Burden': 'Amount of blood clots present',
                'D-Dimer': 'Blood marker indicating clot breakdown',
                'Fibrin Formation': 'Blood clot protein development',
                'Platelet Activation': 'Blood clotting cell function',
                'Endothelial Damage': 'Injury to blood vessel lining',
                'Hypoxemia': 'Low oxygen levels in blood',
                'Chronic Obstruction': 'Long-term blockage of blood vessels',
                'Anticoagulation Status': 'Blood thinning medication effects',
                'Protein Content': 'Amount of protein in pleural fluid',
                'LDH Levels': 'Lactate dehydrogenase enzyme concentration',
                'Pleural Fluid': 'Fluid accumulation around lungs',
                'Underlying Pathology': 'Root cause of disease',
                'Respiratory Mechanics': 'Physical aspects of breathing',
                'Air Leak Size': 'Extent of air escape from lung',
                'Lung Collapse': 'Degree of lung deflation',
                'Pleural Pressure': 'Pressure in space around lungs',
                'Respiratory Distress': 'Difficulty breathing',
                'Healing Response': 'Body\'s repair mechanisms',
                'Recurrence Risk': 'Probability of condition returning',
                'Airway Dilation': 'Abnormal widening of breathing passages',
                'Chronic Infection': 'Long-term bacterial presence',
                'Mucus Clearance': 'Removal of airway secretions',
                'Bacterial Colonization': 'Persistent bacterial growth',
                'NTM Species': 'Type of non-tuberculous mycobacteria',
                'Disease Progression': 'Advancement of condition',
                'Alpha-1 Antitrypsin Levels': 'Concentration of protective enzyme',
                'Protease Activity': 'Protein-breaking enzyme function',
                'Elastin Degradation': 'Breakdown of lung elastic fibers',
                'Genetic Markers': 'DNA indicators of inherited conditions',
                'Liver Function': 'Performance of liver organ',
                'Lung Protection': 'Mechanisms preventing lung damage',
                'Left Heart Function': 'Performance of left heart chambers',
                'Fluid Balance': 'Regulation of body fluid levels',
                'BNP Levels': 'Brain natriuretic peptide heart marker',
                'Cardiac Output': 'Amount of blood pumped by heart',
                'Chemical Exposure': 'Contact with harmful substances',
                'Epithelial Damage': 'Injury to airway lining cells',
                'Repair Mechanisms': 'Body\'s healing processes',
                'Sensitization': 'Development of allergic reactions',
                'Protein Levels': 'Concentration of proteins in pleural fluid',
                'Systemic Circulation': 'Blood flow throughout the body',
                'Trauma Severity': 'Extent of injury damage',
                'Air Leak Volume': 'Amount of air escaping from lung',
                'Pain Response': 'Body\'s reaction to injury',
                'Emergency Stabilization': 'Immediate life-saving measures',
                'Mediastinal Shift': 'Movement of central chest structures',
                'Cardiac Preload': 'Blood volume returning to heart',
                'Emergency Decompression': 'Immediate pressure relief procedure',
                'Blood Volume': 'Amount of blood in pleural space',
                'Coagulation Status': 'Blood clotting ability',
                'Respiratory Compromise': 'Impaired breathing function',
                'Shock Risk': 'Probability of cardiovascular collapse',
                'Surgical Intervention': 'Need for operative treatment',
                'Genetic Factors': 'Inherited influences on disease',
                'Mucus Properties': 'Characteristics of airway secretions',
                'Infection Susceptibility': 'Tendency to develop infections',
                'Fungal Load': 'Amount of fungal organisms present',
                'Tissue Necrosis': 'Death of tissue from infection',
                'Abscess Formation': 'Development of pus-filled cavities',
                'Antifungal Resistance': 'Fungal resistance to medications',
                'Systemic Spread': 'Infection spreading throughout body',
                'Dust Particle Load': 'Amount of particles in lung tissue',
                'Lung Function Decline': 'Progressive loss of respiratory capacity',
                'Occupational History': 'Work-related exposure record',
                'Inflammatory Cytokines': 'Immune signaling molecules',
                'Oxygenation Index': 'Measure of oxygen transfer efficiency',
                'Lung Injury Score': 'Assessment of lung damage severity',
                'Ventilator Settings': 'Mechanical breathing support parameters'
            };
            return details[nt] || 'Respiratory biochemical marker';
        }

        function getSpecificEtalons(category) {
            const etalons = {
                'copd': ['Airflow optimization', 'Gas exchange', 'Respiratory muscle function', 'Inflammation control', 'Mucus clearance', 'Exercise tolerance'],
                'asthma': ['Bronchodilation', 'Inflammation reduction', 'Trigger sensitivity', 'Airway reactivity', 'Mucus regulation', 'Immune balance'],
                'fibrosis': ['Fibrosis progression', 'Gas diffusion', 'Lung compliance', 'Collagen regulation', 'Epithelial repair', 'Inflammatory control'],
                'pneumonia': ['Pathogen clearance', 'Immune response', 'Oxygenation', 'Inflammatory balance', 'Tissue healing', 'Recovery support'],
                'tuberculosis': ['Immune surveillance', 'Granuloma stability', 'Bacterial control', 'Tissue protection', 'Reactivation prevention', 'Healing support'],
                'pulmonary-hypertension': ['Pulmonary pressure', 'Vascular resistance', 'Right heart function', 'Endothelial health', 'Hemodynamics', 'Exercise capacity'],
                'sleep-apnea': ['Airway patency', 'Respiratory control', 'Sleep quality', 'Oxygenation', 'Arousal threshold', 'Muscle tone']
            };
            return etalons[category] || ['Respiratory function', 'Gas exchange', 'Airway patency', 'Inflammation control', 'Immune support', 'Tissue repair'];
        }

        function renderProtocols() {
            const grid = document.getElementById('protocolGrid');
            grid.innerHTML = '';

            filteredProtocols.forEach(protocol => {
                const card = document.createElement('div');
                card.className = `bg-white rounded-lg shadow-md card-hover cursor-pointer category-${protocol.category}`;
                card.onclick = () => openModal(protocol);
                
                card.innerHTML = `
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-lg font-semibold text-gray-900">${protocol.name}</h3>
                            <span class="severity-indicator severity-${protocol.severity}"></span>
                        </div>
                        
                        <div class="text-xs text-sky-600 font-medium mb-2">${protocol.dsm}</div>
                        <div class="text-xs text-blue-600 font-medium mb-2">👥 Age: ${protocol.ageGroup}</div>
                        <div class="text-xs text-green-600 font-medium mb-3">🎯 ${protocol.primarySystems}</div>
                        
                        <p class="text-gray-600 text-sm mb-4">${protocol.description}</p>
                        
                        <div class="flex flex-wrap gap-2 mb-4">
                            ${protocol.regions.slice(0, 2).map(region => 
                                `<span class="px-2 py-1 bg-sky-100 text-sky-700 text-xs rounded-full">🫁 ${region}</span>`
                            ).join('')}
                            ${protocol.regions.length > 2 ? `<span class="text-xs text-gray-500">+${protocol.regions.length - 2} more</span>` : ''}
                        </div>
                        
                        <div class="flex justify-between items-center text-sm text-gray-500 mb-3">
                            <span>⏱️ ${protocol.duration}</span>
                            <span>${protocol.frequencies.length} frequencies</span>
                        </div>
                        
                        <div class="flex flex-wrap gap-1">
                            ${protocol.frequencies.slice(0, 3).map(freq => 
                                `<span class="frequency-badge">${freq}</span>`
                            ).join('')}
                            ${protocol.frequencies.length > 3 ? `<span class="text-xs text-gray-500">+${protocol.frequencies.length - 3} more</span>` : ''}
                        </div>
                    </div>
                `;
                
                grid.appendChild(card);
            });

            // Update total count
            document.getElementById('totalProtocols').textContent = filteredProtocols.length;
        }

        function openModal(protocol) {
            document.getElementById('modalTitle').textContent = protocol.name;
            document.getElementById('modalCategory').textContent = protocol.category.charAt(0).toUpperCase() + protocol.category.slice(1) + ' Condition • Age: ' + protocol.ageGroup;
            document.getElementById('modalDSM').textContent = protocol.dsm;
            
            // Get the modal content container and replace with comprehensive blueprint
            const modalContentContainer = document.getElementById('modalContent');
            modalContentContainer.innerHTML = `
                <div class="space-y-6">
                    <!-- 1. Title and Overview -->
                    <div class="bg-gradient-to-r from-sky-50 to-blue-50 p-6 rounded-lg border border-sky-200">
                        <h3 class="text-xl font-bold text-sky-800 mb-4">📋 1. Title and Overview</h3>
                        <div class="space-y-4">
                            <div>
                                <h4 class="font-semibold text-gray-800 mb-2">What it is:</h4>
                                <p class="text-gray-700">${protocol.description}</p>
                            </div>
                            <div>
                                <h4 class="font-semibold text-gray-800 mb-2">Primary Body Systems Affected:</h4>
                                <p class="text-gray-700 font-medium text-green-700">${protocol.primarySystems}</p>
                            </div>
                            <div>
                                <h4 class="font-semibold text-gray-800 mb-2">How it affects the body:</h4>
                                <p class="text-gray-700">Impacts respiratory function, gas exchange, oxygen delivery, and overall breathing efficiency. Can lead to reduced exercise tolerance, hypoxemia, respiratory failure, and increased risk of complications including pneumonia, respiratory arrest, and cardiovascular strain.</p>
                            </div>
                        </div>
                    </div>

                    <!-- 2. Related Body Parts/Systems -->
                    <div class="bg-gradient-to-r from-blue-50 to-green-50 p-6 rounded-lg border border-blue-200">
                        <h3 class="text-xl font-bold text-blue-800 mb-4">🎯 2. Related Body Parts/Systems & Associated Etalons to Test</h3>
                        
                        <div class="space-y-4">
                            <div class="bg-white p-4 rounded-lg border border-blue-200">
                                <h4 class="font-semibold text-blue-700 mb-3">Category: Primary Respiratory Regions</h4>
                                <div class="space-y-2 text-sm">
                                    ${protocol.regions.map(region => `<div>• <strong>${region}</strong> → ${getRegionDetails(region)}</div>`).join('')}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 rounded-lg border border-blue-200">
                                <h4 class="font-semibold text-blue-700 mb-3">Category: Biochemical & Functional Markers</h4>
                                <div class="space-y-2 text-sm">
                                    ${protocol.neurotransmitters.map(nt => `<div>• <strong>${nt}</strong> → ${getNeurotransmitterDetails(nt)}</div>`).join('')}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 rounded-lg border border-blue-200">
                                <h4 class="font-semibold text-blue-700 mb-3">Category: Specific Respiratory Etalons</h4>
                                <div class="grid grid-cols-2 gap-2 text-sm">
                                    ${getSpecificEtalons(protocol.category).map(etalon => `<div class="bg-blue-50 px-3 py-1 rounded">• ${etalon}</div>`).join('')}
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 3. Energetic Markers -->
                    <div class="bg-gradient-to-r from-green-50 to-yellow-50 p-6 rounded-lg border border-green-200">
                        <h3 class="text-xl font-bold text-green-800 mb-4">🔍 3. Energetic Markers to Look For (NLS Analysis)</h3>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="space-y-3">
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">Visual Icons (Flandler's scale):</h5>
                                    <p class="text-sm text-gray-700">Brown/Red on ${protocol.regions[0]} → ${protocol.category} dysfunction</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">Graph Numbers:</h5>
                                    <p class="text-sm text-gray-700">${protocol.severity === 'mild' ? '2–4' : protocol.severity === 'moderate' ? '3–5' : '4–6'} (unstable ${protocol.category} function)</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">Blue vs Red Lines:</h5>
                                    <p class="text-sm text-gray-700">Divergence in ${protocol.neurotransmitters.slice(0,2).join('/')} patterns</p>
                                </div>
                            </div>
                            
                            <div class="space-y-3">
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">Isoline:</h5>
                                    <p class="text-sm text-gray-700">Fluctuations matching disrupted ${protocol.category} rhythms</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">KCC (Spectral Similarity):</h5>
                                    <p class="text-sm text-gray-700">Low to ${protocol.neurotransmitters.slice(0,2).join(', ')} sets indicates respiratory dysfunction</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-green-200">
                                    <h5 class="font-semibold text-green-700 mb-2">Entropy (E) & Vegetative Test:</h5>
                                    <p class="text-sm text-gray-700">E ~${protocol.severity === 'mild' ? '2–4' : protocol.severity === 'moderate' ? '3–5' : '4–6'} in ${protocol.regions[0]} = respiratory stress<br>+10% with ${protocol.category} rhythm or ${protocol.neurotransmitters[0]} sets indicates positive respiratory balance</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 4. Recommended Protocol -->
                    <div class="bg-gradient-to-r from-yellow-50 to-orange-50 p-6 rounded-lg border border-yellow-200">
                        <h3 class="text-xl font-bold text-yellow-800 mb-4">⚡ 4. Recommended Energetic Protocol</h3>
                        
                        <div class="space-y-4">
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-white p-4 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Initial Scan</h5>
                                    <p class="text-sm text-gray-700">Comprehensive respiratory ${protocol.category === 'copd' ? 'airway and alveolar' : protocol.category === 'asthma' ? 'bronchial and immune' : protocol.category === 'fibrosis' ? 'interstitial and fibrotic' : protocol.category} scan (60–80% intensity for adults).</p>
                                </div>
                                
                                <div class="bg-white p-4 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Focused Analysis</h5>
                                    <p class="text-sm text-gray-700">${protocol.regions.slice(0,3).join(', ')}, associated respiratory pathways.</p>
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 rounded border border-yellow-200">
                                <h5 class="font-semibold text-yellow-700 mb-3">Meta-Therapy – Selection</h5>
                                <div class="grid grid-cols-2 gap-2">
                                    <div class="bg-yellow-50 px-3 py-1 rounded text-sm">• ${protocol.category} optimization</div>
                                    <div class="bg-yellow-50 px-3 py-1 rounded text-sm">• ${protocol.neurotransmitters[0]} enhancement</div>
                                    <div class="bg-yellow-50 px-3 py-1 rounded text-sm">• Respiratory stabilization</div>
                                    <div class="bg-yellow-50 px-3 py-1 rounded text-sm">• Gas exchange support</div>
                                </div>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="bg-white p-3 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Meta-Therapy Settings</h5>
                                    <p class="text-sm text-gray-700">${protocol.severity === 'mild' ? 'Moderate intensity' : protocol.severity === 'moderate' ? 'Standard intensity' : 'Careful progressive intensity'}; 3–5 min cycles for respiratory conditions.</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Sessions</h5>
                                    <p class="text-sm text-gray-700">${protocol.severity === 'mild' ? '2-3 cycles × 2 times/week' : protocol.severity === 'moderate' ? '3 cycles × 2-3 times/week' : '3-4 cycles × 3 times/week'} (reassess every 2-3 weeks).</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Focus</h5>
                                    <p class="text-sm text-gray-700">≤3 priority respiratory etalons per session (avoid system overload).</p>
                                </div>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-white p-3 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Vegetative Test</h5>
                                    <p class="text-sm text-gray-700">${getSpecificEtalons(protocol.category)[0]} + ${getSpecificEtalons(protocol.category)[1]} support.</p>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-yellow-200">
                                    <h5 class="font-semibold text-yellow-700 mb-2">Imprinting</h5>
                                    <p class="text-sm text-gray-700">Water, ${protocol.category === 'asthma' ? 'chamomile tea' : protocol.category === 'copd' ? 'eucalyptus tea' : 'lung-supportive herbal tea'}, or crystal → imprint "${protocol.category} balance" etalons.</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 5. Client Instructions -->
                    <div class="bg-gradient-to-r from-orange-50 to-red-50 p-6 rounded-lg border border-orange-200">
                        <h3 class="text-xl font-bold text-orange-800 mb-4">👤 5. Client Instructions</h3>
                        <div class="space-y-3">
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">${protocol.category === 'asthma' ? 'Identify and avoid triggers, keep rescue inhaler available' : protocol.category === 'copd' ? 'Quit smoking, practice breathing exercises, use medications as prescribed' : protocol.category === 'sleep-apnea' ? 'Use CPAP device as prescribed, maintain healthy weight' : protocol.category === 'pneumonia' ? 'Take antibiotics as prescribed, rest, stay hydrated' : protocol.category === 'tuberculosis' ? 'Take anti-TB medications exactly as prescribed, maintain isolation if active' : protocol.category === 'fibrosis' ? 'Avoid lung irritants, use oxygen therapy as prescribed, consider pulmonary rehabilitation' : protocol.category === 'pulmonary-hypertension' ? 'Take pulmonary hypertension medications as prescribed, monitor exercise tolerance' : 'Follow prescribed treatments and avoid respiratory irritants'}</span></div>
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">Use imprinted remedy ${protocol.category === 'asthma' ? 'during calm periods' : 'as directed'} (5–10 min relaxation for respiratory support)</span></div>
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">Supportive lifestyle measures: ${protocol.category === 'copd' ? 'pulmonary rehabilitation, oxygen therapy as needed' : protocol.category === 'asthma' ? 'allergen avoidance, stress management' : protocol.category === 'sleep-apnea' ? 'weight management, sleep position training' : protocol.category === 'fibrosis' ? 'oxygen therapy, pulmonary rehabilitation, avoid occupational exposures' : protocol.category === 'tuberculosis' ? 'nutritional support, infection control measures' : protocol.category === 'pulmonary-hypertension' ? 'exercise as tolerated, avoid high altitudes' : 'adequate rest, proper nutrition, hydration'}</span></div>
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">Monitor symptoms and report shortness of breath, chest pain, or worsening cough immediately</span></div>
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">Continue all prescribed respiratory medications and coordinate with pulmonologist</span></div>
                            <div class="flex items-start"><span class="text-orange-600 mr-2">•</span><span class="text-gray-700">Maintain emergency contact information and know when to seek immediate medical care</span></div>
                        </div>
                    </div>

                    <!-- 6. Medical Disclaimer -->
                    <div class="bg-gradient-to-r from-red-50 to-pink-50 p-6 rounded-lg border border-red-200">
                        <h3 class="text-xl font-bold text-red-800 mb-4">⚠️ 6. Important Respiratory Medical Disclaimer and Follow-up</h3>
                        
                        <div class="space-y-4">
                            <div class="bg-red-100 p-4 rounded-lg border border-red-300">
                                <h4 class="font-semibold text-red-800 mb-2">🚨 Critical Safety Notes:</h4>
                                <p class="text-sm text-red-700 mb-2">${protocol.notes}</p>
                                <p class="text-sm text-red-700">This protocol is SUPPORTIVE ONLY and never replaces emergency medical care, pulmonology consultation, or prescribed medications. Respiratory conditions can be life-threatening.</p>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-white p-3 rounded border border-red-200">
                                    <h5 class="font-semibold text-red-700 mb-2">Emergency Signs - Seek Immediate Care:</h5>
                                    <ul class="text-sm text-gray-700 space-y-1">
                                        <li>• Severe shortness of breath</li>
                                        <li>• Chest pain or tightness</li>
                                        <li>• Blue lips or fingernails</li>
                                        <li>• Inability to speak in full sentences</li>
                                        <li>• High fever with breathing difficulty</li>
                                        <li>• Coughing up blood</li>
                                    </ul>
                                </div>
                                
                                <div class="bg-white p-3 rounded border border-red-200">
                                    <h5 class="font-semibold text-red-700 mb-2">Required Medical Coordination:</h5>
                                    <ul class="text-sm text-gray-700 space-y-1">
                                        <li>• Pulmonology consultation essential</li>
                                        <li>• Regular lung function monitoring</li>
                                        <li>• Medication compliance critical</li>
                                        <li>• Imaging studies as ordered</li>
                                        <li>• Oxygen therapy management</li>
                                        <li>• Emergency action plan</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 rounded border border-red-200">
                                <h5 class="font-semibold text-red-700 mb-2">Follow-up Protocol:</h5>
                                <p class="text-sm text-gray-700">
                                    Reassess after 2-3 weeks. Monitor respiratory symptoms, medication effects, and exercise tolerance. 
                                    Coordinate with medical team for optimal outcomes. Document any changes in breathing patterns or exercise capacity. 
                                    ${protocol.severity === 'severe' ? 'Weekly medical follow-up recommended.' : 'Regular pulmonology follow-up essential.'}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
            
            document.getElementById('protocolModal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('protocolModal').classList.add('hidden');
        }

        function filterProtocols() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const categoryFilter = document.getElementById('categoryFilter').value;
            const severityFilter = document.getElementById('severityFilter').value;

            filteredProtocols = protocols.filter(protocol => {
                const matchesSearch = protocol.name.toLowerCase().includes(searchTerm) ||
                                    protocol.description.toLowerCase().includes(searchTerm) ||
                                    protocol.regions.some(region => region.toLowerCase().includes(searchTerm)) ||
                                    protocol.neurotransmitters.some(nt => nt.toLowerCase().includes(searchTerm));
                
                const matchesCategory = !categoryFilter || protocol.category === categoryFilter;
                const matchesSeverity = !severityFilter || protocol.severity === severityFilter;

                return matchesSearch && matchesCategory && matchesSeverity;
            });

            renderProtocols();
        }

        // Event listeners
        document.getElementById('searchInput').addEventListener('input', filterProtocols);
        document.getElementById('categoryFilter').addEventListener('change', filterProtocols);
        document.getElementById('severityFilter').addEventListener('change', filterProtocols);

        document.getElementById('toggleMapping').addEventListener('click', function() {
            const content = document.getElementById('mappingContent');
            const button = this;
            
            if (content.classList.contains('hidden')) {
                content.classList.remove('hidden');
                button.textContent = 'Hide Mapping Guide';
            } else {
                content.classList.add('hidden');
                button.textContent = 'Show Mapping Guide';
            }
        });

        // Close modal when clicking outside
        document.getElementById('protocolModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Initialize
        renderProtocols();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'976ab3c8443373fd',t:'MTc1NjQ1NjM5My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
