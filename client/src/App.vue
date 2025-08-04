<script setup>
  function openFolder(folderType) {
    console.log(`Membuka folder: ${folderType}`);
    // Animate card
    event.target.closest('.folder-card').style.transform = 'scale(0.95)';
    setTimeout(() => {
        event.target.closest('.folder-card').style.transform = '';
    }, 150);
    
    // Di sini bisa ditambahkan navigasi ke halaman folder
    alert(`Membuka folder ${folderType}`);
  }

  function openBookmark(bookmarkId) {
    console.log(`Membuka bookmark: ${bookmarkId}`);
    // Animate item
    event.target.closest('.bookmark-item').style.background = '#333';
    setTimeout(() => {
        event.target.closest('.bookmark-item').style.background = '';
    }, 200);
    
    alert(`Membuka bookmark ${bookmarkId}`);
  }

  function addBookmark() {
    console.log('Menambah bookmark baru');
    // Animate button
    document.querySelector('.floating-button').style.transform = 'scale(0.9)';
    setTimeout(() => {
        document.querySelector('.floating-button').style.transform = '';
    }, 150);
    
    alert('Menambah bookmark baru');
  }

  // Menu toggle functionality
  document.querySelector('.menu-icon').addEventListener('click', function() {
    this.style.transform = 'rotate(90deg)';
    setTimeout(() => {
        this.style.transform = '';
    }, 200);
    alert('Menu dibuka');
  });

  // Search functionality
  document.querySelector('.search-icon').addEventListener('click', function() {
    alert('Fitur pencarian');
  });

  // Profile functionality
  document.querySelector('.profile-icon').addEventListener('click', function() {
    alert('Profil pengguna');
  });
</script>
<template>
  <div class="header">
        <div class="header-left">
            <div class="menu-icon">
                <div class="menu-line"></div>
                <div class="menu-line"></div>
                <div class="menu-line"></div>
            </div>
            <div class="logo">
                <div class="logo-icon">B</div>
                <div class="logo-text">Bookmarkly</div>
            </div>
        </div>
        <div class="header-right">
            <div class="search-icon">🔍</div>
            <div class="profile-icon">JD</div>
        </div>
    </div>

    <div class="main-content">
        <div class="section-title">Folder Bookmark</div>
        
        <div class="folders-grid">
            <div class="folder-card" onclick="openFolder('work')">
                <div class="folder-cover work">
                    <div class="folder-icon">💼</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Kerja</div>
                    <div class="folder-count">24 bookmark</div>
                </div>
            </div>

            <div class="folder-card" onclick="openFolder('design')">
                <div class="folder-cover design">
                    <div class="folder-icon">🎨</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Design</div>
                    <div class="folder-count">18 bookmark</div>
                </div>
            </div>

            <div class="folder-card" onclick="openFolder('development')">
                <div class="folder-cover development">
                    <div class="folder-icon">💻</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Development</div>
                    <div class="folder-count">32 bookmark</div>
                </div>
            </div>

            <div class="folder-card" onclick="openFolder('resources')">
                <div class="folder-cover resources">
                    <div class="folder-icon">📚</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Resources</div>
                    <div class="folder-count">15 bookmark</div>
                </div>
            </div>

            <div class="folder-card" onclick="openFolder('learning')">
                <div class="folder-cover learning">
                    <div class="folder-icon">🎓</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Learning</div>
                    <div class="folder-count">21 bookmark</div>
                </div>
            </div>

            <div class="folder-card" onclick="openFolder('personal')">
                <div class="folder-cover">
                    <div class="folder-icon">⭐</div>
                </div>
                <div class="folder-info">
                    <div class="folder-name">Personal</div>
                    <div class="folder-count">9 bookmark</div>
                </div>
            </div>
        </div>

        <div class="recent-section">
            <div class="section-title">Bookmark Terbaru</div>
            <div class="recent-bookmarks">
                <div class="bookmark-item" onclick="openBookmark('github')">
                    <div class="bookmark-favicon">🐙</div>
                    <div class="bookmark-info">
                        <div class="bookmark-title">GitHub - React Projects</div>
                        <div class="bookmark-url">github.com/user/react-projects</div>
                    </div>
                </div>

                <div class="bookmark-item" onclick="openBookmark('figma')">
                    <div class="bookmark-favicon">🎨</div>
                    <div class="bookmark-info">
                        <div class="bookmark-title">Figma Design System</div>
                        <div class="bookmark-url">figma.com/design-system</div>
                    </div>
                </div>

                <div class="bookmark-item" onclick="openBookmark('docs')">
                    <div class="bookmark-favicon">📖</div>
                    <div class="bookmark-info">
                        <div class="bookmark-title">API Documentation</div>
                        <div class="bookmark-url">docs.example.com/api</div>
                    </div>
                </div>

                <div class="bookmark-item" onclick="openBookmark('medium')">
                    <div class="bookmark-favicon">📝</div>
                    <div class="bookmark-info">
                        <div class="bookmark-title">Medium Article - UX Design</div>
                        <div class="bookmark-url">medium.com/ux-design-article</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <button class="floating-button" onclick="addBookmark()">+</button>
</template>

<style>
  * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
  }

  body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background: #121212;
      color: #ffffff;
      min-height: 100vh;
  }

  .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px 20px;
      background: #1e1e1e;
      border-bottom: 1px solid #333;
  }

  .header-left {
      display: flex;
      align-items: center;
      gap: 16px;
  }

  .menu-icon {
      width: 24px;
      height: 24px;
      background: #333;
      border-radius: 4px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 3px;
      padding: 4px;
      cursor: pointer;
  }

  .menu-line {
      height: 2px;
      background: #fff;
      border-radius: 1px;
  }

  .logo {
      display: flex;
      align-items: center;
      gap: 8px;
  }

  .logo-icon {
      width: 32px;
      height: 32px;
      background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 16px;
  }

  .logo-text {
      font-size: 20px;
      font-weight: 600;
      color: #fff;
  }

  .header-right {
      display: flex;
      align-items: center;
      gap: 16px;
  }

  .search-icon, .profile-icon {
      width: 32px;
      height: 32px;
      background: #333;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
  }

  .profile-icon {
      background: linear-gradient(135deg, #667eea, #764ba2);
      font-size: 14px;
      font-weight: bold;
  }

  .main-content {
      padding: 20px;
  }

  .section-title {
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 16px;
      color: #fff;
  }

  .folders-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
      margin-bottom: 32px;
  }

  .folder-card {
      background: #1e1e1e;
      border-radius: 12px;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .folder-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.4);
  }

  .folder-cover {
      width: 100%;
      height: 120px;
      background: linear-gradient(135deg, #667eea, #764ba2);
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
  }

  .folder-cover.work {
      background: linear-gradient(135deg, #f093fb, #f5576c);
  }

  .folder-cover.design {
      background: linear-gradient(135deg, #4facfe, #00f2fe);
  }

  .folder-cover.development {
      background: linear-gradient(135deg, #43e97b, #38f9d7);
  }

  .folder-cover.resources {
      background: linear-gradient(135deg, #fa709a, #fee140);
  }

  .folder-cover.learning {
      background: linear-gradient(135deg, #a8edea, #fed6e3);
  }

  .folder-icon {
      font-size: 32px;
      color: white;
      text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
  }

  .folder-info {
      padding: 12px;
  }

  .folder-name {
      font-size: 14px;
      font-weight: 600;
      color: #fff;
      margin-bottom: 4px;
  }

  .folder-count {
    font-size: 12px;
    color: #aaa;
  }

  .recent-section {
    margin-top: 32px;
  }

  .recent-bookmarks {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .bookmark-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px;
    background: #1e1e1e;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.2s ease;
  }

  .bookmark-item:hover {
    background: #2a2a2a;
  }

  .bookmark-favicon {
    width: 40px;
    height: 40px;
    background: #333;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
  }

  .bookmark-info {
    flex: 1;
  }

  .bookmark-title {
    font-size: 14px;
    font-weight: 500;
    color: #fff;
    margin-bottom: 2px;
  }

  .bookmark-url {
    font-size: 12px;
    color: #aaa;
  }

  .floating-button {
      position: fixed;
    bottom: 24px;
    right: 24px;
    width: 56px;
    height: 56px;
    background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 4px 16px rgba(255, 107, 107, 0.4);
    cursor: pointer;
    transition: transform 0.2s ease;
    border: none;
    color: white;
    font-size: 24px;
  }

  .floating-button:hover {
      transform: scale(1.1);
  }
</style>