<script setup>
import { ref } from 'vue';

// Data is separated for better maintainability
const profile = ref({
  name: 'Fahime Zivdar',
  role: 'Senior Android Engineer',
  email: 'Fahime.zivdar.it@gmail.com',
  linkedin: 'linkedin.com/in/fahime-zivdar',
  linkedinUrl: 'https://linkedin.com/in/fahime-zivdar',
  bio: 'Senior Android Engineer with 8+ years of experience building scalable Android and Android TV applications. Specialized in modern Android development with deep expertise in video streaming, TV navigation, and performance optimization.',
  achievements: 'Proven track record of reducing crashes, improving UX, and delivering high-impact products across e-commerce, media, and gaming domains.',
  skills: [
    'Kotlin', 
    'Jetpack Compose', 
    'Clean Architecture', 
    'Android TV', 
    'Video Streaming', 
    'Performance Opt'
  ]
});
</script>

<template>
  <div class="profile-wrapper">
    <div class="background-glow"></div>
    
    <div class="profile-card">
      <!-- Header Section -->
      <header class="card-header">
        <div class="avatar-placeholder">
          <span>FZ</span>
        </div>
        <h1>{{ profile.name }}</h1>
        <h2>{{ profile.role }}</h2>
      </header>

      <!-- Contact Actions -->
      <div class="contact-actions">
        <a :href="`mailto:${profile.email}`" class="action-btn email">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
          <span>Email Me</span>
        </a>
        <a :href="profile.linkedinUrl" target="_blank" rel="noopener noreferrer" class="action-btn linkedin">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
          <span>LinkedIn</span>
        </a>
      </div>

      <!-- Main Content -->
      <div class="card-content">
        <div class="section-title">
          <h3>Profile</h3>
          <div class="divider"></div>
        </div>
        
        <p class="bio-text">
          {{ profile.bio }}
        </p>
        
        <p class="bio-text secondary">
          {{ profile.achievements }}
        </p>

        <!-- Skills Tags -->
        <div class="skills-container">
          <span v-for="skill in profile.skills" :key="skill" class="skill-tag">
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Define Variables for easy theming */
:root {
  --bg-dark: #0f1115;
  --card-bg: rgba(30, 34, 45, 0.7);
  --primary: #818cf8; /* Indigo-400 */
  --primary-glow: rgba(129, 140, 248, 0.2);
  --text-main: #f3f4f6;
  --text-muted: #9ca3af;
  --border: rgba(255, 255, 255, 0.1);
}

body {
  padding: 0;
  margin: 0;
}

.profile-wrapper {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #0f1115;
  background-image: radial-gradient(at 0% 0%, rgba(56, 189, 248, 0.1) 0px, transparent 50%),
                    radial-gradient(at 100% 100%, rgba(129, 140, 248, 0.1) 0px, transparent 50%);
  font-family: 'Inter', system-ui, -apple-system, sans-serif;
  position: relative;
  overflow: hidden;
}

/* Glass Card */
.profile-card {
  width: 100%;
  max-width: 700px;
  background: rgba(30, 34, 45, 0.6);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 24px;
  padding: 3rem;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  gap: 2rem;
  position: relative;
  z-index: 10;
}

/* Header */
.card-header {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.avatar-placeholder {
  width: 80px;
  height: 80px;
  border-radius: 20px;
  background: linear-gradient(135deg, #6366f1, #a855f7);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  box-shadow: 0 10px 20px rgba(99, 102, 241, 0.3);
}

.avatar-placeholder span {
  font-size: 1.75rem;
  font-weight: 700;
  color: white;
  letter-spacing: 1px;
}

h1 {
  font-size: 2.25rem;
  font-weight: 700;
  color: #f3f4f6;
  margin: 0 0 0.5rem 0;
  letter-spacing: -0.025em;
}

h2 {
  font-size: 1rem;
  font-weight: 500;
  color: #818cf8;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin: 0;
}

/* Contact Actions */
.contact-actions {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.action-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.25rem;
  border-radius: 12px;
  font-size: 0.9rem;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.2s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.action-btn.email {
  background: rgba(255, 255, 255, 0.05);
  color: #e5e7eb;
}

.action-btn.linkedin {
  background: rgba(10, 102, 194, 0.15);
  color: #60a5fa;
  border-color: rgba(10, 102, 194, 0.3);
}

.action-btn:hover {
  transform: translateY(-2px);
  background: rgba(255, 255, 255, 0.1);
}

/* Content */
.section-title {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.section-title h3 {
  font-size: 0.875rem;
  font-weight: 600;
  color: #9ca3af;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin: 0;
  white-space: nowrap;
}

.divider {
  height: 1px;
  width: 100%;
  background: rgba(255, 255, 255, 0.1);
}

.bio-text {
  font-size: 1.05rem;
  line-height: 1.75;
  color: #d1d5db;
  margin-bottom: 1rem;
}

.bio-text.secondary {
  color: #9ca3af;
  font-size: 1rem;
}

/* Skills */
.skills-container {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 2rem;
}

.skill-tag {
  padding: 0.5rem 1rem;
  background: rgba(129, 140, 248, 0.1);
  color: #a5b4fc;
  border: 1px solid rgba(129, 140, 248, 0.2);
  border-radius: 100px;
  font-size: 0.85rem;
  font-weight: 500;
  transition: all 0.2s ease;
}

.skill-tag:hover {
  background: rgba(129, 140, 248, 0.2);
  color: #fff;
  border-color: rgba(129, 140, 248, 0.4);
}

/* Mobile Responsiveness */
@media (max-width: 640px) {
  .profile-card {
    padding: 2rem 1.5rem;
  }
  
  .contact-actions {
    flex-direction: column;
    width: 100%;
  }
  
  .action-btn {
    justify-content: center;
  }
  
  h1 {
    font-size: 1.75rem;
  }
}
</style>