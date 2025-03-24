<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CoreX Multifunctional Platform</title>
  <!-- Google Fonts: Josefin Sans -->
  <link href="https://fonts.googleapis.com/css2?family=Josefin+Sans&display=swap" rel="stylesheet">
  <!-- Google Material Icons -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Josefin Sans', sans-serif;
    }
    body {
      display: flex;
      flex-direction: column;
      height: 100vh;
      background: #fff;
      transition: background 0.3s, color 0.3s;
    }
    /* Top Bar (Artistic Blue) */
    .topbar {
      display: flex;
      align-items: center;
      background: #3a8ec9; /* Artistic Blue */
      padding: 0 15px;
      height: 60px;
      color: #fff;
    }
    .topbar .icon-group {
      display: flex;
      gap: 20px;
      align-items: center;
    }
    .topbar .icon-group span {
      cursor: pointer;
      font-size: 24px;
    }
    .search-bars {
      margin-left: auto;
      display: flex;
      gap: 10px;
    }
    .search-bars input {
      padding: 8px;
      border-radius: 6px;
      border: 1px solid #ccc;
      font-size: 16px;
    }
    .theme-toggle {
      margin-left: 20px;
      cursor: pointer;
      background: #fff;
      color: #3a8ec9;
      padding: 6px 12px;
      border: none;
      border-radius: 6px;
      font-size: 16px;
    }
    /* Main wrapper: Sidebar + Content */
    .wrapper {
      flex: 1;
      display: flex;
    }
    /* Sidebar (Light Grey) */
    .sidebar {
      width: 240px;
      background: #e0e0e0;
      padding: 15px;
      overflow-y: auto;
    }
    .sidebar h2 {
      margin-bottom: 15px;
      font-size: 20px;
      text-align: center;
    }
    .sidebar .logo {
      font-weight: bold;
      font-size: 24px;
      margin-bottom: 15px;
      text-align: center;
      text-transform: uppercase;
    }
    .sidebar .nav-item {
      display: flex;
      align-items: center;
      gap: 10px;
      cursor: pointer;
      margin: 10px 0;
      padding: 8px;
      background: #fff;
      border: 1px solid #ccc;
      border-radius: 8px;
      transition: background 0.3s;
    }
    .sidebar .nav-item:hover {
      background: #d0d0d0;
    }
    .sidebar .nav-item span.material-icons {
      font-size: 28px;
    }
    /* Main Content Area */
    .main-content {
      flex: 1;
      padding: 25px;
      overflow-y: auto;
      text-align: center;
    }
    .main-content h1, .main-content h2 {
      margin-bottom: 20px;
    }
    .main-content p, .main-content li {
      font-size: 18px;
      line-height: 1.5;
    }
    /* Button Styling for main area */
    .main-btn {
      display: inline-block;
      margin: 10px;
      padding: 12px 20px;
      font-size: 18px;
      background: #3a8ec9;
      color: #fff;
      text-decoration: none;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .main-btn:hover {
      background: #317bb7;
    }
    /* Bottom Bar */
    .bottombar {
      display: flex;
      align-items: center;
      justify-content: space-around;
      background: #ffcc00;
      height: 60px;
    }
    .bottombar .bottom-item {
      cursor: pointer;
      font-weight: bold;
      font-size: 18px;
      padding: 8px 12px;
      background: #fff;
      border: 1px solid #ccc;
      border-radius: 8px;
      transition: background 0.3s;
    }
    .bottombar .bottom-item:hover {
      background: #f0f0f0;
    }
    /* Dark Theme Overrides */
    body.dark {
      background: #333;
      color: #f0f0f0;
    }
    body.dark .topbar {
      background: #1a4f7a;
    }
    body.dark .theme-toggle {
      background: #333;
      color: #f0f0f0;
    }
    body.dark .sidebar {
      background: #444;
    }
    body.dark .sidebar .nav-item {
      background: #555;
      border: 1px solid #666;
    }
    body.dark .sidebar .nav-item:hover {
      background: #666;
    }
    body.dark .main-btn {
      background: #1a4f7a;
    }
    body.dark .main-btn:hover {
      background: #14566a;
    }
    body.dark .bottombar {
      background: #666;
    }
    body.dark .bottombar .bottom-item {
      background: #555;
      border: 1px solid #777;
    }
    body.dark .bottombar .bottom-item:hover {
      background: #666;
    }
  </style>
</head>
<body>
  <!-- TOP BAR -->
  <div class="topbar">
    <div class="icon-group">
      <!-- Account -->
      <span class="material-icons" onclick="accountFunction()">account_circle</span>
      <!-- Favorites -->
      <span class="material-icons" onclick="favoritesFunction()">star</span>
      <!-- Team -->
      <span class="material-icons" onclick="teamFunction()">groups</span>
      <!-- Time -->
      <span class="material-icons" onclick="timeFunction()">access_alarm</span>
      <!-- AI Options -->
      <span class="material-icons" onclick="showAIOptions()">smart_toy</span>
      <!-- Tasks -->
      <span class="material-icons" onclick="tasksFunction()">check_circle</span>
    </div>
    <div class="search-bars">
      <input type="text" placeholder="Global Search..." onkeyup="globalSearch(this.value)">
      <input type="text" placeholder="Local Search..." onkeyup="localSearch(this.value)">
    </div>
    <button class="theme-toggle" onclick="toggleTheme()">Toggle Theme</button>
  </div>

  <!-- MAIN WRAPPER: Sidebar + Main Content -->
  <div class="wrapper">
    <!-- SIDEBAR -->
    <div class="sidebar">
      <div class="logo">CoreX</div>
      <h2>CoreX Platform</h2>
    <!-- Assignment -->
<div class="nav-item" onclick="assignmentFunction()">
  <span class="material-icons">history</span>
  <span>Assignment</span>
</div>
      <!-- Home -->
      <div class="nav-item" onclick="showHome()">
        <span class="material-icons">home</span>
        <span>Home</span>
      </div>
      <!-- Apps -->
      <div class="nav-item" onclick="showApps()">
        <span class="material-icons">apps</span>
        <span>Apps</span>
      </div>
      <!-- File (Google Drive) -->
      <div class="nav-item" onclick="openLink('https://drive.google.com')">
        <span class="material-icons">cloud</span>
        <span>File</span>
      </div>
      <!-- Tools -->
      <div class="nav-item" onclick="showTools()">
        <span class="material-icons">construction</span>
        <span>Tools</span>
      </div>
      <!-- Solver -->
      <div class="nav-item" onclick="showSolver()">
        <span class="material-icons">calculate</span>
        <span>Solver</span>
      </div>
      <!-- My Learning -->
      <div class="nav-item" onclick="showMyLearning()">
        <span class="material-icons">school</span>
        <span>My Learning</span>
      </div>
      <!-- Social Dashboard -->
      <div class="nav-item" onclick="showSocialDashboard()">
        <span class="material-icons">dashboard</span>
        <span>Social</span>
      </div>
      <!-- Archive -->
      <div class="nav-item" onclick="archiveFunction()">
        <span class="material-icons">archive</span>
        <span>Archive</span>
      </div>
      <!-- Lock -->
      <div class="nav-item" onclick="lockFunction()">
        <span class="material-icons">lock</span>
        <span>Lock</span>
      </div>
    </div>
    <!-- MAIN CONTENT -->
    <div class="main-content" id="main-content">
      <h1>Welcome to CoreX</h1>
      <p>Select an option from the sidebar or top bar to begin.</p>
    </div>
  </div>

  <!-- BOTTOM BAR -->
  <div class="bottombar">
    <div class="bottom-item" onclick="showAboutMenu()">About</div>
    <div class="bottom-item" onclick="showNetworking()">Networkings</div>
    <div class="bottom-item" onclick="showNotifications()">Notifications</div>
    <div class="bottom-item" onclick="showSettings()">Settings</div>
  </div>

  <script>
    // Basic Functions for demonstration purposes

    function accountFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Account Settings</h2><p>Manage your account, login, logout, and profile settings.</p>";
    }
    function favoritesFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Favorites</h2><p>Your favorite files, courses, and links are shown here.</p>";
    }
    function teamFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Team Management</h2><p>Manage team projects, chat, meetings, and badges.</p>";
    }
    function timeFunction() {
      const now = new Date();
      document.getElementById("main-content").innerHTML =
        "<h2>Current Time</h2><p>" + now.toLocaleTimeString() + "</p>";
    }
    function tasksFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Tasks & Projects</h2><p>Manage your tasks and projects here.</p>";
    }
    function globalSearch(query) {
      document.getElementById("main-content").innerHTML =
        "<h2>Global Search</h2><p>Searching for: " + query + "</p>";
    }
    function localSearch(query) {
      document.getElementById("main-content").innerHTML =
        "<h2>Local Search</h2><p>Searching for local files: " + query + "</p>";
    }
    function recentsFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Recents</h2><p>These are your recently viewed items.</p>";
    }
    function showHome() {
      const html = `
        <h2>Home</h2>
        <button class="main-btn">Customized</button>
        <button class="main-btn" onclick="openLink('https://www.bbc.com/news')">News</button>
        <button class="main-btn">Ongoing Learnings</button>
        <button class="main-btn" onclick="openLink('https://www.youtube.com')">YouTube</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showApps() {
      const html = `
        <h2>Apps</h2>
        <button class="main-btn" onclick="openLink('https://territorial.io')">Game (Territorial)</button>
        <button class="main-btn" onclick="openLink('https://www.canva.com/')">Canva</button>
        <button class="main-btn" onclick="openLink('https://www.pinterest.com/')">Pinterest</button>
        <button class="main-btn" onclick="openLink('https://firefly.adobe.com/')">Adobe Firefly</button>
        <button class="main-btn" onclick="openLink('https://web.telegram.org/')">Telegram Web</button>
        <button class="main-btn" onclick="openLink('https://example.com/dongaLMS')">dongaLMS</button>
        <button class="main-btn" onclick="openLink('https://miro.com/')">Miro</button>
        <button class="main-btn" onclick="openLink('https://github.com/')">GitHub</button>
        <button class="main-btn" onclick="openLink('https://www.binance.com/')">Binance</button>
        <button class="main-btn" onclick="openLink('https://zapier.com/')">AI Automations</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showTools() {
      const html = `
        <h2>Tools</h2>
<!-- Update links for YouTube, PDF, MP4 to MP3 -->
<li><a href="https://en1.savefrom.net/1-youtube-video-downloader-7ON/" class="menu-item">YouTube Downloader</a></li>
<li><a href="https://www.ilovepdf.com/" class="menu-item">PDF Converter</a></li>
<li><a href="https://www.freeconvert.com/mp4-to-mp3" class="menu-item">MP4 to MP3</a></li>

      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showSolver() {
      const html = `
        <h2>Solver</h2>
        <button class="main-btn" onclick="openLink('https://www.symbolab.com/calculators')">Math Solver (Symbolab)</button>
        <button class="main-btn" onclick="openLink('https://www.desmos.com/')">Graphing Calculator (Desmos)</button>
        <button class="main-btn" onclick="openLink('https://www.geogebra.org/graphing?lang=en')">GeoGebra</button>
        <button class="main-btn" onclick="openLink('https://www.wolframalpha.com/')">Wolfram Alpha</button>
        <button class="main-btn" onclick="openLink('https://www.mathway.com/BasicMath')">Mathway</button>
        <button class="main-btn" onclick="openLink('https://apps.kde.org/categories/')">KDE Apps</button>
        <button class="main-btn" onclick="openLink('https://www.sagemath.org/')">SageMath</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showMyLearning() {
      const html = `
        <h2>My Learning</h2>
        <button class="main-btn" onclick="openLink('https://www.udemy.com/')">Udemy</button>
        <button class="main-btn" onclick="openLink('https://www.nvidia.com/en-us/training/')">NVIDIA Academy</button>
        <div style="margin:20px 0;">
          <strong>Linear Algebra:</strong><br>
          <button class="main-btn" onclick="openLink('https://tutorial.math.lamar.edu/')">Paul's Notes</button>
          <button class="main-btn" onclick="openLink('https://www.googleadservices.com/pagead/aclk?...')">MIT Math</button>
          <button class="main-btn" onclick="openLink('https://www.khanacademy.org/')">Khan Academy</button>
          <button class="main-btn" onclick="openLink('https://openstax.org/subjects/math')">Math (OpenStax)</button>
          <button class="main-btn" onclick="openLink('https://openstax.org/subjects/math')">Statistics (OpenStax)</button>
        </div>
        <button class="main-btn" onclick="openLink('https://www.deeplearning.ai/')">Deep Learning</button>
        <button class="main-btn" onclick="openLink('http://neuralnetworksanddeeplearning.com/')">Neural Network & Deep</button>
        <button class="main-btn" onclick="openLink('https://cs50.harvard.edu/ai/')">Harvard Data Science</button>
        <button class="main-btn" onclick="openLink('https://www.datacamp.com/')">DataCamp</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showSocialDashboard() {
      const html = `
        <h2>Social Dashboard</h2>
        <button class="main-btn" onclick="openLink('https://www.facebook.com/login/')">Facebook</button>
        <button class="main-btn" onclick="openLink('https://www.instagram.com/accounts/login/')">Instagram</button>
        <button class="main-btn" onclick="openLink('https://twitter.com/login/')">Twitter (X)</button>
        <button class="main-btn" onclick="openLink('https://www.tiktok.com/login')">TikTok</button>
        <button class="main-btn" onclick="openLink('https://www.pinterest.com/login/')">Pinterest</button>
        <button class="main-btn" onclick="openLink('https://web.telegram.org/')">Telegram</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showAIOptions() {
      const html = `
        <h2>AI Assistant Options</h2>
        <button class="main-btn" onclick="openLink('https://chat.openai.com/')">ChatGPT</button>
        <button class="main-btn">Claude</button>
        <button class="main-btn">Google Gemini</button>
        <button class="main-btn">DeepSeek AI</button>
        <button class="main-btn">Others</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showAboutMenu() {
      const html = `
        <h2>About Section</h2>
        <button class="main-btn" onclick="showAboutCoreX()">About CoreX</button>
        <button class="main-btn" onclick="showAboutDeveloper()">About the Developer</button>
        <button class="main-btn" onclick="showContacts()">Contacts</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showAboutCoreX() {
      const html = `
        <h2>About CoreX</h2>
        <p><strong>Welcome to CoreX – Your Ultimate Digital Hub!</strong></p>
        <p>CoreX is a <strong>powerful, multifunctional platform</strong> designed to streamline your workflow and consolidate all essential tools in one place.</p>
        <h3>What CoreX Offers:</h3>
        <ul>
          <li>Task & Project Management</li>
          <li>Global & Local Search</li>
          <li>AI Assistance</li>
          <li>Time Management</li>
          <li>Team Collaboration</li>
          <li>Favorites & Quick Access</li>
          <li>File & Tool Management</li>
          <li>Math Solver & Calculators</li>
          <li>Learning Resources</li>
          <li>Social Dashboard</li>
          <li>Security & Privacy</li>
          <li>Archives & Trash</li>
          <li>Meetings & Calls</li>
        </ul>
        <p><strong>CoreX simplifies your digital life.</strong> Get started and experience the future of productivity!</p>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showAboutDeveloper() {
      const html = `
        <h2>About the Developer</h2>
        <p>CoreX is developed by <strong>Shavkatjon Yuldashev</strong>, a dedicated innovator focused on creating intuitive and efficient digital solutions.</p>
        <h3>Developer’s Vision:</h3>
        <ul>
          <li>Build an all-in-one digital hub.</li>
          <li>Provide AI-powered assistance.</li>
          <li>Create a secure, user-friendly workspace.</li>
          <li>Continuously innovate with the latest technology.</li>
        </ul>
        <p>"I created CoreX to simplify digital workflows and empower productivity. This is just the beginning!"</p>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showContacts() {
      const html = `
        <h2>Contacts</h2>
        <p><strong>Stay Connected</strong></p>
        <p>📧 Email: shavkatjon.yuldashev.0411@gmail.com</p>
        <p>📱 Instagram: <a href="https://www.instagram.com/shavkatjon_l/" target="_blank">@shavkatjon_l</a></p>
        <p>🌐 Website: <em>Your Website (if available)</em></p>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showNetworking() {
      const html = `
        <h2>Networkings</h2>
        <button class="main-btn" onclick="openLink('https://www.zoom.com/')">Zoom</button>
        <button class="main-btn" onclick="openLink('https://web.whatsapp.com/')">WhatsApp</button>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showNotifications() {
      const html = `
        <h2>Notifications</h2>
        <ul>
          <li>Personal Chat</li>
          <li>Group Chat</li>
          <li>Supergroups</li>
          <li>Bots</li>
          <li>Comments</li>
        </ul>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function showSettings() {
      const html = `
        <h2>Settings</h2>
        <ul>
          <li>General Settings</li>
          <li>Theme Layout</li>
          <li>Language</li>
          <li>Reading Mode</li>
        </ul>
      `;
      document.getElementById("main-content").innerHTML = html;
    }
    function archiveFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Archive</h2><p>Archive functionality activated. Here you can view and manage archived items.</p>";
    }
    function lockFunction() {
      document.getElementById("main-content").innerHTML =
        "<h2>Locked Files</h2><p>Accessing locked files. Authentication required.</p>";
    }
    function openLink(url) {
      window.open(url, "_blank");
    }
    // Theme Toggle Functionality
    function toggleTheme() {
      document.body.classList.toggle("dark");
    }
  </script>
</body>
</html>
