<template>
    <div class="profile-card">
      <!-- Header Section: Displays profile photo, name, location, and action icons -->
      <div class="profile-header">
        <!-- Profile photo in circular style -->
        <img class="profile-photo" :src="photoUrl" alt="Profile photo" />
        <!-- Candidate's name and location -->
        <h1>{{ name }}</h1>
        <p>{{ location }}</p>
        <!-- Action icons for messaging and saving the candidate -->
        <div class="action-icons">
          <button @click="sendMessage">💬</button> <!-- Message icon button -->
          <button @click="saveCandidate">✅</button> <!-- Save icon button -->
        </div>
      </div>
  
      <!-- Profile Details Sections: Skills, Domain, Experience, and Portfolio -->
      <div class="profile-sections">
        <!-- Skills section -->
        <section>
          <h2>SKILLS</h2>
          <p>{{ skills }}</p> <!-- Display candidate's skills -->
        </section>
        <!-- Domain section -->
        <section>
          <h2>DOMAIN</h2>
          <p>{{ domain }}</p> <!-- Display candidate's domain expertise -->
        </section>
        <!-- Experience section as a list of previous positions -->
        <section>
          <h2>EXPERIENCE</h2>
          <ul>
            <li v-for="(exp, index) in experience" :key="index">{{ exp }}</li> <!-- Loop through experience array -->
          </ul>
        </section>
        <!-- Portfolio section with images -->
        <section>
          <h2>PORTFOLIO</h2>
          <p>{{ portfolioText }}</p> <!-- Intro text for portfolio -->
          <div class="portfolio-images">
            <img v-for="(image, index) in portfolioImages" :src="image" :key="index" /> <!-- Loop through portfolio images -->
          </div>
        </section>
      </div>
  
      <!-- Download Icon: A button to download portfolio or resume -->
      <div class="download-icon">
        <button @click="downloadPortfolio">⬇️</button> <!-- Download icon button -->
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'; // Import ref to define reactive data
  import photo from '../assets/img/olla2.jpg';
  import Portfolio1 from '../assets/img/hod.jpg';
  import Portfolio2 from '../assets/img/house-of-the-dragon-ka-1920.jpg';
  import Portfolio3 from '../assets/img/image.jpg';
  import Portfolio4 from '../assets/img/images.jpg';
  
  // Profile data variables
  const photoUrl = ref(photo); // Profile photo (replace with your image in assets folder)
  const name = ref("Robert D."); // Candidate name
  const location = ref("Los Angeles, USA"); // Candidate location
  const skills = ref("UI Design, UX Design, Graphic Design, Web Design, Android, iOS"); // Candidate skills
  const domain = ref("Design & Multimedia"); // Candidate domain expertise
  const experience = ref([
    "UX, UI Designer at ACME Inc. - 2009 to PRESENT",
    "UX Designer at ION5 Inc. - 2006 to 2009",
    "Design intern at Simply9 Inc. - 2005 to 2006",
  ]); // Experience array listing past positions
  const portfolioText = ref("Take a look at a few samples of my web and mobile work."); // Portfolio intro text
  const portfolioImages = ref([
    (Portfolio1),
    (Portfolio2),
    (Portfolio3),
    (Portfolio4)
  ]); // Array of portfolio image paths
  
  // Methods for button actions
  const sendMessage = () => alert("Messaging the candidate..."); // Placeholder for message button
  const saveCandidate = () => alert("Candidate saved!"); // Placeholder for save button
  const downloadPortfolio = () => alert("Downloading portfolio..."); // Placeholder for download button
  </script>
  
  <style scoped>
  /* Profile Card Container: Centered and styled with dark background */
  .profile-card {
    max-width: 600px;
    margin: 0 auto;
    background-color: rgba(0, 0, 0, 0.884);
    color: #ffffff;
    padding: 20px;
    border-radius: 16px;
    
  }
  
  /* Header Section Styling */
  .profile-header {
    position: relative;
    padding: 20px;
    background-image: url(../assets/img/MOUNTAIN.jpg);
    background-size: cover;
    
    
  }
  .profile-photo {
    
    width: 120px;
    height: 120px;
    border-radius: 50%; /* Circular profile photo */
    margin: 0 auto;
  }
  
  h1 {
    font-size: 40px;
    margin: 10px 0 5px;
    text-align: center;
  }
  
  p {
    font-size: 15px;
    color: #cccccc;
    text-align: center;
  }
  .action-icons {
    display: flex;
    gap: 15px;
    justify-content: center;
    margin-top: 10px;
  }
  .action-icons button {
    font-size: 24px;
    color: #ffffff;
    background: none;
    border: none;
    cursor: pointer;
  }
  
  /* Styling for Profile Sections */
  .profile-sections section {
    margin: 20px 0;
    
  }

  .profile-sections h2 {
    font-size: 30px;
    color: #ffffff;
    font-weight: bold;
    text-align: left;
    margin-bottom: 10px;
  }
  .profile-sections p, .profile-sections ul {
    font-size: 14px;
    color: #cccccc;
    text-align: left;
  }
  .portfolio-images {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap; /* Allows multiple rows for images */
  }
  .portfolio-images img {
    width: 70px;
    height: 70px;
    border-radius: 4px; /* Rounded corners for images */
  }
  
  /* Download Icon Styling */
  .download-icon {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
  .download-icon button {
    font-size: 24px;
    color: #ffffff;
    background: none;
    border: none;
    cursor: pointer;
  }
  </style>
  