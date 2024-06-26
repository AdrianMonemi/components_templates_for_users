# Responsive Sidebar | (HTML SASS & Javascript)

![thumbnail](thumbnail.png)

# Code Snippets

## HTML5
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Sidebar</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <div class="wrapper">
      <div class="sidebar">
        <div class="profile">
          <div class="logo">
            <img src="images/logo-icon.svg" alt="Logo" />
            <span class="logo-txt">Teams.co</span>
          </div>
          <img src="images/profile.svg" alt="Logo" class="profile-img" />
          <div class="profile-content">
            <h2 class="name text-white">Aman</h2>
            <span class="position text-dark">Product Designer</span>
          </div>
        </div>

        <ul class="menu">
          <li class="list active">
            <a href="#dashboard" class="link">
              <img src="images/icon-01.svg" alt="icon" />
              <span>Dashboard</span>
            </a>
          </li>
          <li class="list">
            <a href="#teams" class="link">
              <img src="images/icon-02.svg" alt="icon" />
              <span>Teams</span>
            </a>
          </li>
          <li class="list">
            <a href="#payments" class="link">
              <img src="images/icon-03.svg" alt="icon" />
              <span>Payments</span>
            </a>
          </li>
          <li class="list">
            <a href="#attendance" class="link">
              <img src="images/icon-04.svg" alt="icon" />
              <span>Attendance</span>
            </a>
          </li>
          <li class="list">
            <a href="#!" class="settings">
              <img src="images/icon-05.svg" alt="icon" />
              <span>Settings</span>
            </a>
          </li>
        </ul>

        <div class="create-teams">
          <div class="create-teams-content">
            <img src="images/icon-dot.svg" alt="icon" class="icon-dot" />
            <img src="images/create-team.svg" alt="icon" class="teams-icon" />
            <h3 class="teams-title text-white">Create Teams</h3>
            <p class="teams-description text-dark">
              Increase your speed with more members
            </p>
          </div>
        </div>
      </div>
      <div class="content">
        <section id="dashboard">
          <h1 class="section-heading">Dashboard</h1>
        </section>
        <section id="teams">
          <h1 class="section-heading">Teams</h1>
        </section>
        <section id="payments">
          <h1 class="section-heading">Payments</h1>
        </section>
        <section id="attendance">
          <h1 class="section-heading">Attendance</h1>
        </section>
      </div>
    </div>
    <script src="script.js"></script>
  </body>
</html>
```
## Compile CSS
```css
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap");
*,
*:before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style-type: none;
  text-decoration: none;
}

html {
  scroll-behavior: smooth;
}

body {
  background: #28283f;
  font-family: "Poppins", sans-serif;
}

.text-white {
  color: #fff;
}

.text-dark {
  color: rgba(255, 255, 255, 0.4);
}

.section-heading {
  color: #fff;
}

.content section {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.content section:nth-child(even) {
  background: rgba(23, 23, 37, 0.8);
}

.wrapper .sidebar {
  position: fixed;
  left: 0;
  overflow-y: scroll;
  width: 15rem;
  height: 100%;
  background: #2e2e48;
  border-radius: 0 3rem 3rem 0;
  padding: 0 0 2rem 0;
  box-shadow: 0 0.1rem 1rem rgba(23, 23, 37, 0.8);
}
.wrapper .sidebar::-webkit-scrollbar {
  width: 0;
}
.wrapper .sidebar .profile {
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 0;
}
.wrapper .sidebar .profile .logo {
  display: flex;
  align-items: center;
  gap: 0.7rem;
}
.wrapper .sidebar .profile .logo img {
  width: 2rem;
  height: auto;
  object-fit: cover;
}
.wrapper .sidebar .profile .logo .logo-txt {
  color: #fff;
  font-weight: bold;
  font-size: 1.7rem;
}
.wrapper .sidebar .profile .profile-img {
  width: 8rem;
  height: 5rem;
  object-fit: contain;
}
.wrapper .sidebar .menu .list {
  padding: 0.4rem 1.5rem;
  margin: 1rem 0;
  position: relative;
  transition: all 0.5s ease-in-out;
}
.wrapper .sidebar .menu .list::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 0.2rem;
  height: 100%;
  background: #7e73ff;
  border-radius: 0.2rem;
  opacity: 0;
  transition: all 0.5s ease-in-out;
  pointer-events: none;
}
.wrapper .sidebar .menu .list:hover::before, .wrapper .sidebar .menu .list.active::before {
  opacity: 1;
  transition: all 0.5s ease-in-out;
}
.wrapper .sidebar .menu .list .link, .wrapper .sidebar .menu .list .settings {
  display: flex;
  align-items: center;
  gap: 1rem;
  color: #fff;
}
.wrapper .sidebar .create-teams {
  width: 90%;
  margin: 0 auto;
  background: linear-gradient(230.04deg, #483fbd 2.11%, rgba(46, 46, 72, 0) 102.63%);
  filter: drop-shadow(0rem 0.4rem 3.3rem rgba(0, 0, 0, 0.25));
  border-radius: 1rem;
  padding: 1rem;
  box-shadow: 0 0 1rem #28283f;
  position: relative;
}
.wrapper .sidebar .create-teams .icon-dot {
  position: absolute;
  top: 1rem;
  right: 1rem;
}
.wrapper .content {
  margin-left: 15rem;
  width: calc(100% - 15rem);
}
@media (max-width: 628px) {
  .wrapper .sidebar {
    overflow-x: hidden;
    border-radius: 0 1rem 1rem 0;
    width: 4rem;
  }
  .wrapper .sidebar .logo-txt {
    display: none;
  }
  .wrapper .sidebar .list {
    margin: 0.5rem 0 !important;
    padding: 0.5rem 0 !important;
  }
  .wrapper .sidebar .list.active::before {
    opacity: 1;
    transform: scale(1);
  }
  .wrapper .sidebar .list::before {
    opacity: 0;
    transform: scale(0);
    width: 2.7rem !important;
    height: 80% !important;
    top: 0.3rem !important;
    left: 0.5rem !important;
    border-radius: 1rem !important;
    z-index: -1 !important;
    background: rgba(95, 95, 167, 0.368627451) !important;
    filter: drop-shadow(0px 4.01974px 34.1678px rgba(0, 0, 0, 0.28));
  }
  .wrapper .sidebar .list .link img, .wrapper .sidebar .list .settings img {
    padding: 0.5rem 1rem;
  }
  .wrapper .sidebar .profile {
    gap: 1rem;
  }
  .wrapper .sidebar .profile-img {
    width: 2.5rem !important;
    height: 2.5rem !important;
  }
  .wrapper .sidebar .profile-content {
    display: none;
  }
  .wrapper .sidebar .create-teams {
    display: none;
  }
  .wrapper .content {
    margin-left: 4rem;
    width: calc(100% - 4rem);
  }
}
```
## Javascript
```javascript
let links = document.querySelectorAll('.list .link');
let sections = document.querySelectorAll('section[id]');

links.forEach((link) => {
  link.addEventListener('click', (e) => {
    e.preventDefault();
    let href = link.getAttribute('href');
    document.querySelector(`${href}`).scrollIntoView({ behavior: 'smooth' });
  });
});

window.addEventListener('scroll', () => {
  let scrollY = window.pageYOffset;
  sections.forEach((section) => {
    const sectionHeight = section.offsetHeight;
    const sectionTop = section.offsetTop - 200;
    const sectionId = section.getAttribute('id');
    if (scrollY > sectionTop && scrollY < sectionTop + sectionHeight) {
      document
        .querySelector(`.list a[href*="${sectionId}"]`)
        .parentElement.classList.add('active');
    } else {
      document
        .querySelector(`.list a[href*="${sectionId}"]`)
        .parentElement.classList.remove('active');
    }
  });
});
```
