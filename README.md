<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MySocial</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background-color: #f0f2f5;
    }

    .navbar {
      background-color: #4267B2;
      color: white;
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .navbar h1 {
      font-size: 1.5rem;
    }

    .container {
      display: flex;
      margin: 1rem;
    }

    .sidebar {
      width: 20%;
      padding: 1rem;
    }

    .feed {
      width: 60%;
      padding: 1rem;
    }

    .post-box {
      background: white;
      padding: 1rem;
      margin-bottom: 1rem;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    .post-box textarea {
      width: 100%;
      border: 1px solid #ccc;
      border-radius: 5px;
      padding: 0.5rem;
      resize: none;
    }

    .post-box button {
      margin-top: 0.5rem;
      padding: 0.5rem 1rem;
      background-color: #4267B2;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .post {
      background: white;
      padding: 1rem;
      margin-bottom: 1rem;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    .rightbar {
      width: 20%;
      padding: 1rem;
    }

    @media (max-width: 768px) {
      .container {
        flex-direction: column;
      }

      .sidebar, .rightbar, .feed {
        width: 100%;
      }
    }
  </style>
  <script>
    window.addEventListener('DOMContentLoaded', function() {
      console.log('[DEBUG] DOMContentLoaded event triggered');

      const postBox = document.querySelector('.post-box');
      console.log('[DEBUG] postBox:', postBox);

      const postButton = postBox ? postBox.querySelector('button') : null;
      console.log('[DEBUG] postButton:', postButton);

      const textarea = postBox ? postBox.querySelector('textarea') : null;
      console.log('[DEBUG] textarea:', textarea);

      if (postButton && textarea) {
        console.log('[DEBUG] postButton and textarea found, adding event listener');

        postButton.addEventListener('click', function() {
          console.log('[DEBUG] Post button clicked');

          const content = textarea.value.trim();
          console.log('[DEBUG] Raw content:', textarea.value);
          console.log('[DEBUG] Trimmed content:', content);

          if (content) {
            alert('Post submitted: ' + content);
            console.log('[DEBUG] Post submitted:', content);
            textarea.value = '';
            console.log('[DEBUG] Textarea cleared');
          } else {
            alert('Post content is empty');
            console.log('[DEBUG] Post content was empty');
          }
        });
      } else {
        console.log('[DEBUG] postButton or textarea not found');
      }
    });
  </script>
</head>
<body>
  <div class="navbar">
    <h1>MySocial</h1>
    <div>
      <a href="#" style="color:white; margin-right: 1rem;">Home</a>
      <a href="#" style="color:white;">Profile</a>
    </div>
  </div>

  <div class="container">
    <div class="sidebar">
      <h3>Navigation</h3>
      <ul>
        <li>Friends</li>
        <li>Groups</li>
        <li>Settings</li>
      </ul>
    </div>

    <div class="feed">
      <div class="post-box">
        <textarea rows="3" placeholder="What's on your mind?"></textarea>
        <button>Post</button>
      </div>

      <div class="post">
        <strong>Jane Doe</strong>
        <p>Enjoying a sunny day at the park!</p>
      </div>

      <div class="post">
        <strong>John Smith</strong>
        <p>Just started learning HTML and CSS. Loving it!</p>
      </div>
    </div>

    <div class="rightbar">
      <h3>Suggestions</h3>
      <p>Follow @alex</p>
      <p>Follow @emily</p>
    </div>
  </div>
</body>
</html>
