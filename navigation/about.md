---
layout: post
title: About
permalink: /about/
comments: true
---

<style>
  body {
    background-color: #FFB6C1; 
    color: black !important;    
  }

  figure {
    display: inline-block;
    text-align: center;
    margin: 20px;
  }

  figcaption {
    color: black !important;
    margin-top: 5px;
    font-weight: bold;
  }

  li, p, h1, h2, h3, h4, h5, h6, a {
    color: black !important;
  }

  img {
    margin: 5px;
  }

  /* Style for confetti button */
  #confetti-button {
    background-color: #FF69B4;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    font-weight: bold;
    border-radius: 10px;
    cursor: pointer;
    margin: 20px 0;
  }

  #confetti-button:hover {
    background-color: #ff85c1;
  }
</style>

### Here are some places I have lived

<p>
  <figure style="display:inline-block; text-align:center; margin-right:20px;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/Flag_of_California.svg" alt="California Flag" width="150">
    <figcaption>California</figcaption>
  </figure>

  <figure style="display:inline-block; text-align:center;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/b/b5/Flag_of_Michigan.svg" alt="Michigan Flag" width="150">
    <figcaption>Michigan</figcaption>
  </figure>
</p>



### Education Journey

These are the schools I have attended

- 🏫 I went to Monterey Ridge Elemetary School from 2014 to 2022
- 🏫 I went to Oak Valley Middle School from 2020 to 2023
- 🎓 I am currently attending Del Norte High School and will graduate in 2027.


<h4>Both my parents are from China</h4>

<p>
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/86/Flag_of_the_People%27s_Republic_of_China_%28cropped%29.svg" alt="China Flag" width="150">
</p>


### Fun Facts About Me

- I'm on the cheer team
- I have a little sister who is 12
- I do not have any pets
- I grew up figure skating 
- My favorite color is light pink

**Here are some pictures of me and my friends**

<img src="https://github.com/user-attachments/assets/1450c8f9-cc68-49cc-b2f9-88a03db6f6e7" alt="IMG_0085" width="200">
<img src="https://github.com/user-attachments/assets/3801d010-fcd3-43f6-a608-2e8e8378478a" alt="IMG_6719" width="200">
<img src="https://github.com/user-attachments/assets/0d1e6d1c-452f-4d61-8b0f-af3b9df26379" alt="IMG_6878" width="200">
<img src="https://github.com/user-attachments/assets/1016f276-2dac-475f-b42e-dd4d786ae4bf" alt="IMG_8483" width="200">
<img src="https://github.com/user-attachments/assets/0589e31c-d986-4a56-81f1-39c8a850ed50" alt="IMG_8490" width="200">



<!-- Confetti Button -->
<button id="confetti-button">🎉 Celebrate!</button>

<!-- Confetti library -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
  document.getElementById('confetti-button').addEventListener('click', () => {
    // Fire confetti
    confetti({
      particleCount: 200,
      spread: 100,
      origin: { y: 0.6 }
    });
  });
</script>