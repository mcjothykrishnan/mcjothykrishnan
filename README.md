- 👋 Hi, I’m Jothy Krishnan M C






 .navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  color: #fff;
}

.navbar ul {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0;
  padding: 0;
  list-style: none;
}

.navbar li {
  margin: 0;
}

.navbar a {
  display: block;
  padding: 1rem;
  color: #fff;
  text-decoration: none;
}

.navbar a:hover {
  background-color: #555;
}

.navbar a.active {
  background-color: #555;
}

section {
  height: 100vh;
  padding: 2rem;
}

h2 {
  margin-top: 0;
}


window.addEventListener("scroll", function () {
  let navbar = document.querySelector(".navbar");
  let sections = document.querySelectorAll("section");
  let currentSection = "";

  sections.forEach(function (section) {
    let sectionTop = section.offsetTop;
    let sectionHeight = section.clientHeight;

    if (pageYOffset >= sectionTop - sectionHeight / 3) {
      currentSection = section.getAttribute("id");
    }
  });

  let activeLink = document.querySelector(".navbar a.active");
  if (activeLink) {
    activeLink.classList.remove("active");
  }

  let newActiveLink = document.querySelector(
    '.navbar a[href="#' + currentSection + '"]'
  );
  if (newActiveLink) {
    newActiveLink.classList.add("active");
  }

  navbar.classList.toggle("scrolled", pageYOffset > 0);
});


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <nav class="navbar">
      <ul>
        <li><a href="#section-1">Section 1</a></li>
        <li><a href="#section-2">Section 2</a></li>
        <li><a href="#section-3">Section 3</a></li>
        <li><a href="#section-4">Section 4</a></li>
      </ul>
    </nav>

    <section id="section-1">
      <h2>Section 1</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ac libero
        ut ex vestibulum pharetra.
      </p>
    </section>

    <section id="section-2">
      <h2>Section 2</h2>
      <p>
        Mauris vel lorem ac purus tincidunt tempor eget a odio. Donec suscipit
        diam sit amet felis lacinia aliquam.
      </p>
    </section>

    <section id="section-3">
      <h2>Section 3</h2>
      <p>
        Integer ut tortor libero. Sed rhoncus urna et tellus luctus, vel
        scelerisque massa dapibus.
      </p>
    </section>

    <section id="section-4">
      <h2>Section 4</h2>
      <p>
        Nunc eu ipsum ac velit blandit volutpat. Curabitur euismod nulla nec
        feugiat vestibulum.
      </p>
    </section>
    <script src="./js.js"></script>
  </body>
</html>
