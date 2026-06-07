
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>NYOTA Fund - National Youth Opportunities Towards Advancement</title>
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
            color: #333;
        }

        /* Header */
        .header {
            background: rgba(255,255,255,0.95);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo h1 {
            color: #667eea;
            font-size: 1.5rem;
        }

        .logo p {
            font-size: 0.8rem;
            color: #666;
        }

        .nav-links {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #667eea;
        }

        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 2rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 3rem;
            border-radius: 20px;
            text-align: center;
            margin-bottom: 2rem;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero .amount {
            font-size: 3rem;
            font-weight: bold;
            margin: 1rem 0;
            color: #ffd700;
        }

        .hero button {
            background: #ffd700;
            color: #333;
            border: none;
            padding: 1rem 2rem;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.3s;
            margin-top: 1rem;
        }

        .hero button:hover {
            transform: scale(1.05);
        }

        /* Cards Grid */
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card h3 {
            color: #667eea;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .card .icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        /* Eligibility Checker */
        .eligibility-section {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .eligibility-section h2 {
            color: #667eea;
            margin-bottom: 1.5rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
        }

        .btn {
            background: #667eea;
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: background 0.3s;
        }

        .btn:hover {
            background: #5a67d8;
        }

        .result {
            margin-top: 1rem;
            padding: 1rem;
            border-radius: 8px;
            display: none;
        }

        .result.success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
            display: block;
        }

        .result.error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
            display: block;
        }

        /* Application Form */
        .application-form {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            display: none;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .application-form h2 {
            color: #667eea;
            margin-bottom: 1.5rem;
        }

        /* County Tracker */
        .county-tracker {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
        }

        .county-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1rem;
            margin-top: 1rem;
        }

        .county-item {
            padding: 0.8rem;
            background: #f7f7f7;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .badge {
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .badge.active {
            background: #28a745;
            color: white;
        }

        .badge.upcoming {
            background: #ffc107;
            color: #333;
        }

        /* Scam Alert */
        .scam-alert {
            background: #fff3cd;
            border-left: 4px solid #ffc107;
            padding: 1rem;
            margin: 1rem 0;
            border-radius: 8px;
        }

        .scam-alert h4 {
            color: #856404;
            margin-bottom: 0.5rem;
        }

        /* Footer */
        .footer {
            background: #2d3748;
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 2rem;
        }

        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 1rem;
            }
            .hero h1 {
                font-size: 1.8rem;
            }
            .hero .amount {
                font-size: 2rem;
            }
            .container {
                padding: 0 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <div class="nav-container">
            <div class="logo">
                <h1>🇰🇪 NYOTA Fund</h1>
                <p>National Youth Opportunities Towards Advancement</p>
            </div>
            <div class="nav-links">
                <a href="#" onclick="showSection('home')">Home</a>
                <a href="#" onclick="showSection('eligibility')">Eligibility</a>
                <a href="#" onclick="showSection('counties')">Counties</a>
                <a href="#" onclick="showApplication()">Apply Now</a>
            </div>
        </div>
    </div>

    <div class="container">
        <!-- Hero Section -->
        <div id="homeSection">
            <div class="hero">
                <h1>Empowering Kenya's Youth</h1>
                <div class="amount">KSh 5 Billion Fund</div>
                <p>In partnership with the World Bank | 100% Grants - No Repayment</p>
                <button onclick="showApplication()">Start Your Application →</button>
            </div>

            <div class="grid-3">
                <div class="card">
                    <div class="icon">💰</div>
                    <h3>Up to KSh 50,000 Grant</h3>
                    <p>Non-repayable funding for youth-led businesses and skills training.</p>
                </div>
                <div class="card">
                    <div class="icon">🎓</div>
                    <h3>Skills Training</h3>
                    <p>Free vocational and digital skills training programs.</p>
                </div>
                <div class="card">
                    <div class="icon">🤝</div>
                    <h3>Mentorship</h3>
                    <p>Access to experienced business mentors and networking opportunities.</p>
                </div>
            </div>

            <div class="scam-alert">
                <h4>⚠️ OFFICIAL NYOTA ALERT</h4>
                <p>The official NYOTA application is done via USSD code <strong>*254#</strong>. No payment is required at any stage. Beware of fraudsters asking for money!</p>
            </div>
        </div>

        <!-- Eligibility Checker -->
        <div id="eligibilitySection" style="display:none;">
            <div class="eligibility-section">
                <h2>📋 Check Your Eligibility</h2>
                <div class="form-group">
                    <label>Age (years)</label>
                    <input type="number" id="age" placeholder="Enter your age">
                </div>
                <div class="form-group">
                    <label>Education Level</label>
                    <select id="education">
                        <option value="">Select</option>
                        <option value="below_form4">Below Form 4</option>
                        <option value="form4">Form 4 Completed</option>
                        <option value="above_form4">Above Form 4</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Employment Status</label>
                    <select id="employment">
                        <option value="">Select</option>
                        <option value="unemployed">Unemployed</option>
                        <option value="underemployed">Underemployed</option>
                        <option value="employed">Employed</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Do you have a National ID?</label>
                    <select id="hasId">
                        <option value="">Select</option>
                        <option value="yes">Yes</option>
                        <option value="no">No</option>
                    </select>
                </div>
                <button class="btn" onclick="checkEligibility()">Check Eligibility</button>
                <div id="eligibilityResult" class="result"></div>
            </div>
        </div>

        <!-- Application Form -->
        <div id="applicationSection" class="application-form">
            <h2>📝 NYOTA Fund Application Form</h2>
            <div class="form-group">
                <label>Full Name</label>
                <input type="text" id="fullName" placeholder="Enter your full name">
            </div>
            <div class="form-group">
                <label>ID Number</label>
                <input type="text" id="idNumber" placeholder="National ID Number">
            </div>
            <div class="form-group">
                <label>Phone Number (Registered SIM)</label>
                <input type="tel" id="phone" placeholder="07XX XXX XXX">
            </div>
            <div class="form-group">
                <label>County</label>
                <select id="county">
                    <option>Nairobi</option>
                    <option>Mombasa</option>
                    <option>Kisumu</option>
                    <option>Nakuru</option>
                    <option>Kiambu</option>
                    <option>Uasin Gishu</option>
                    <option>Machakos</option>
                    <option>Kajiado</option>
                </select>
            </div>
            <div class="form-group">
                <label>Business Idea / Skills Training Interest</label>
                <textarea id="businessIdea" rows="3" placeholder="Describe your business idea or what skills you want to learn"></textarea>
            </div>
            <div class="form-group">
                <label>Do you have a registered SIM card in your name?</label>
                <select id="hasSim">
                    <option value="yes">Yes</option>
                    <option value="no">No</option>
                </select>
            </div>
            <button class="btn" onclick="submitApplication()">Submit Application</button>
            <div id="applicationResult" class="result"></div>
        </div>

        <!-- County Tracker -->
        <div id="countiesSection" style="display:none;">
            <div class="county-tracker">
                <h2>🗺️ NYOTA Fund County Rollout Tracker</h2>
                <p>Check if your county is currently active for NYOTA applications</p>
                <div class="county-list" id="countyList"></div>
                <div class="scam-alert" style="margin-top: 1rem;">
                    <h4>📱 Apply via USSD</h4>
                    <p>Dial <strong>*254#</strong> on your Safaricom, Airtel, or Telkom line to apply officially.</p>
                </div>
            </div>
        </div>
    </div>

    <div class="footer">
        <p>© 2024 NYOTA Fund - Government of Kenya in partnership with World Bank</p>
        <p style="margin-top: 0.5rem; font-size: 0.8rem;">Official USSD: *254# | No fees required at any stage</p>
    </div>

    <script>
        // County Data
        const counties = [
            { name: "Nairobi", status: "active" },
            { name: "Mombasa", status: "active" },
            { name: "Kisumu", status: "active" },
            { name: "Nakuru", status: "active" },
            { name: "Kiambu", status: "active" },
            { name: "Uasin Gishu", status: "active" },
            { name: "Machakos", status: "active" },
            { name: "Kajiado", status: "active" },
            { name: "Kilifi", status: "upcoming" },
            { name: "Kwale", status: "upcoming" },
            { name: "Turkana", status: "upcoming" },
            { name: "Mandera", status: "upcoming" },
            { name: "Garissa", status: "upcoming" },
            { name: "Wajir", status: "upcoming" },
            { name: "Kakamega", status: "upcoming" },
            { name: "Bungoma", status: "upcoming" },
            { name: "Busia", status: "upcoming" },
            { name: "Meru", status: "upcoming" },
            { name: "Embu", status: "upcoming" },
            { name: "Nyeri", status: "upcoming" },
            { name: "Kirinyaga", status: "upcoming" },
            { name: "Murang'a", status: "upcoming" },
            { name: "Laikipia", status: "upcoming" },
            { name: "Samburu", status: "upcoming" },
            { name: "Isiolo", status: "upcoming" },
            { name: "Marsabit", status: "upcoming" },
            { name: "Tana River", status: "upcoming" },
            { name: "Lamu", status: "upcoming" }
        ];

        // Display County List
        function displayCounties() {
            const container = document.getElementById('countyList');
            if (!container) return;
            
            container.innerHTML = '';
            counties.forEach(county => {
                const div = document.createElement('div');
                div.className = 'county-item';
                div.innerHTML = `
                    <span>${county.name}</span>
                    <span class="badge ${county.status}">${county.status === 'active' ? '✅ Active' : '📅 Upcoming'}</span>
                `;
                container.appendChild(div);
            });
        }

        // Navigation Functions
        function showSection(section) {
            document.getElementById('homeSection').style.display = section === 'home' ? 'block' : 'none';
            document.getElementById('eligibilitySection').style.display = section === 'eligibility' ? 'block' : 'none';
            document.getElementById('countiesSection').style.display = section === 'counties' ? 'block' : 'none';
            document.getElementById('applicationSection').style.display = 'none';
            
            if (section === 'counties') {
                displayCounties();
            }
        }

        function showApplication() {
            document.getElementById('homeSection').style.display = 'none';
            document.getElementById('eligibilitySection').style.display = 'none';
            document.getElementById('countiesSection').style.display = 'none';
            document.getElementById('applicationSection').style.display = 'block';
        }

        // Eligibility Check
        function checkEligibility() {
            const age = parseInt(document.getElementById('age').value);
            const education = document.getElementById('education').value;
            const employment = document.getElementById('employment').value;
            const hasId = document.getElementById('hasId').value;
            const resultDiv = document.getElementById('eligibilityResult');
            
            let eligible = true;
            let message = '';
            
            if (isNaN(age) || age < 18) {
                eligible = false;
                message = '❌ You must be at least 18 years old.';
            } else if (age > 35) {
                eligible = false;
                message = '❌ Age limit is 18-35 years (up to 35 for persons with disabilities).';
            } else if (education !== 'form4' && education !== 'below_form4') {
                eligible = false;
                message = '❌ You must have completed Form 4 or below.';
            } else if (employment !== 'unemployed' && employment !== 'underemployed') {
                eligible = false;
                message = '❌ You must be unemployed or underemployed.';
            } else if (hasId !== 'yes') {
                eligible = false;
                message = '❌ You must have a valid National ID.';
            } else {
                message = '✅ Congratulations! You are eligible for the NYOTA Fund. Click "Apply Now" to submit your application.';
            }
            
            resultDiv.className = eligible ? 'result success' : 'result error';
            resultDiv.innerHTML = message;
            
            if (eligible) {
                setTimeout(() => {
                    showApplication();
                }, 2000);
            }
        }

        // Submit Application
        function submitApplication() {
            const fullName = document.getElementById('fullName').value;
            const idNumber = document.getElementById('idNumber').value;
            const phone = document.getElementById('phone').value;
            const county = document.getElementById('county').value;
            const businessIdea = document.getElementById('businessIdea').value;
            const hasSim = document.getElementById('hasSim').value;
            const resultDiv = document.getElementById('applicationResult');
            
            if (!fullName || !idNumber || !phone || !county || !businessIdea) {
                resultDiv.className = 'result error';
                resultDiv.innerHTML = '❌ Please fill in all fields before submitting.';
                return;
            }
            
            if (phone.length < 10) {
                resultDiv.className = 'result error';
                resultDiv.innerHTML = '❌ Please enter a valid 10-digit phone number.';
                return;
            }
            
            if (hasSim !== 'yes') {
                resultDiv.className = 'result error';
                resultDiv.innerHTML = '❌ You need a SIM card registered in your name to apply for NYOTA Fund.';
                return;
            }
            
            // Store application in localStorage
            const applications = JSON.parse(localStorage.getItem('nyota_applications') || '[]');
            const newApp = {
                id: Date.now(),
                fullName,
                idNumber,
                phone,
                county,
                businessIdea,
                date: new Date().toISOString(),
                status: 'pending'
            };
            applications.push(newApp);
            localStorage.setItem('nyota_applications', JSON.stringify(applications));
            
            resultDiv.className = 'result success';
            resultDiv.innerHTML = `
                ✅ Application submitted successfully!<br><br>
                <strong>Next Steps:</strong><br>
                1. Dial <strong>*254#</strong> on your registered SIM to complete official verification<br>
                2. You will be contacted for a business aptitude test<br>
                3. Physical validation will be scheduled at your nearest NYOTA center<br><br>
                <strong>Reference ID:</strong> NYOTA-${newApp.id}<br>
                <strong>Status:</strong> Pending Review
            `;
            
            // Clear form
            document.getElementById('fullName').value = '';
            document.getElementById('idNumber').value = '';
            document.getElementById('phone').value = '';
            document.getElementById('businessIdea').value = '';
            
            // Scroll to result
            resultDiv.scrollIntoView({ behavior: 'smooth' });
        }

        // Load counties on page load
        document.addEventListener('DOMContentLoaded', () => {
            displayCounties();
        });
    </script>
</body>
</html>
