# Ex.07 Restaurant Website
## Date:18.05.2025
## Reg no:212224220055

## AIM:
To develop a static Restaurant website to display the food items and services provided by them.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS.

### Step 3:
Updating the sample content.

### Step 4:
Choose the appropriate style and color scheme.

### Step 5:
Validate the layout in various browsers.

### Step 6:
Validate the HTML code.

### Step 7:
Publish the website in the given URL.

## PROGRAM:
```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Food Monster Restaurant</title>
<style>
  :root {
    --warm-orange: #e85a4f;
    --dark-slate: #2d3436;
    --cream: #f7f1e1;
    --light-shadow: rgba(0,0,0,0.1);
  }

  * {
    box-sizing: border-box;
  }
  body {
    margin: 0; font-family: 'Arial', sans-serif;
    background-color: var(--cream);
    color: var(--dark-slate);
    scroll-behavior: smooth;
  }

  header {
    background-color: var(--dark-slate);
    color: var(--cream);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 2px 5px var(--light-shadow);
  }
  header h1 {
    margin: 0; font-weight: 700;
    font-size: 1.8rem;
    letter-spacing: 1.2px;
  }
  nav a {
    color: var(--cream);
    text-decoration: none;
    margin-left: 1.8rem;
    font-weight: 600;
    font-size: 1rem;
    transition: color 0.3s ease;
  }
  nav a:hover, nav a:focus {
    color: var(--warm-orange);
    outline: none;
  }
  nav a.active {
    color: var(--warm-orange);
    border-bottom: 2px solid var(--warm-orange);
    padding-bottom: 2px;
  }

  #home {
    background: url('https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
    height: 90vh;
    color: var(--cream);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 1rem;
  }
  #home h2 {
    font-size: 3rem;
    margin-bottom: 0.5rem;
    text-shadow: 0 2px 6px rgba(0,0,0,0.7);
  }
  #home p {
    font-size: 1.5rem;
    max-width: 600px;
    margin-bottom: 1.5rem;
    text-shadow: 0 1px 4px rgba(0,0,0,0.6);
  }
  #home button {
    background-color: var(--warm-orange);
    border: none;
    color: var(--cream);
    font-weight: 700;
    padding: 0.75rem 2rem;
    font-size: 1.2rem;
    cursor: pointer;
    border-radius: 30px;
    box-shadow: 0 4px 10px rgba(232,90,79,0.7);
    transition: background-color 0.3s ease;
  }
  #home button:hover, #home button:focus {
    background-color: #d04845;
    outline: none;
  }

  section {
    padding: 4rem 2rem 3rem;
    max-width: 1100px;
    margin: 0 auto;
  }

  #menu h2 {
    text-align: center;
    font-size: 2.4rem;
    color: var(--warm-orange);
    margin-bottom: 2rem;
  }
  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(220px, 1fr));
    gap: 2rem;
  }
  .menu-item {
    background-color: var(--cream);
    box-shadow: 0 2px 8px var(--light-shadow);
    border-radius: 12px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    transition: transform 0.3s ease;
  }
  .menu-item:hover {
    transform: translateY(-5px);
  }
  .menu-item img {
    width: 100%;
    height: 140px;
    object-fit: cover;
  }
  .menu-item-content {
    padding: 1rem;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }
  .menu-item-content h3 {
    margin: 0 0 0.4rem 0;
    font-size: 1.2rem;
    color: var(--dark-slate);
  }
  .menu-item-content p {
    margin: 0.3rem 0 0 0;
    flex-grow: 1;
    font-size: 0.95rem;
    color: #444;
  }
  .menu-item-content .price {
    margin-top: 0.8rem;
    font-weight: 700;
    color: var(--warm-orange);
    font-size: 1.1rem;
  }

  #administration h2 {
    text-align: center;
    font-size: 2.4rem;
    color: var(--warm-orange);
    margin-bottom: 2rem;
  }
  .admin-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(180px,1fr));
    gap: 2rem;
    justify-items: center;
  }
  .admin-member {
    background-color: var(--cream);
    box-shadow: 0 2px 8px var(--light-shadow);
    border-radius: 15px;
    padding: 1rem;
    width: 180px;
    text-align: center;
    transition: box-shadow 0.3s ease;
  }
  .admin-member:hover {
    box-shadow: 0 6px 20px rgba(232,90,79,0.6);
  }
  .admin-member img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 0.8rem;
    border: 3px solid var(--warm-orange);
  }
  .admin-member h3 {
    margin: 0.4rem 0 0.2rem 0;
    font-size: 1.2rem;
    color: var(--dark-slate);
  }
  .admin-member p {
    margin: 0; font-size: 0.9rem;
    color: #666;
  }

  #contact h2 {
    text-align: center;
    font-size: 2.4rem;
    color: var(--warm-orange);
    margin-bottom: 2rem;
  }
  .contact-info {
    max-width: 500px;
    margin: 0 auto;
    background-color: var(--cream);
    padding: 2rem;
    border-radius: 12px;
    box-shadow: 0 2px 8px var(--light-shadow);
    font-size: 1.1rem;
    color: var(--dark-slate);
    line-height: 1.6;
  }
  .contact-info strong {
    color: var(--warm-orange);
  }

  footer {
    background-color: var(--dark-slate);
    color: var(--cream);
    text-align: center;
    padding: 1.5rem 1rem;
    font-size: 0.9rem;
    letter-spacing: 0.04rem;
    user-select: none;
    margin-top: 3rem;
  }

  @media (max-width: 480px) {
    #home h2 {
      font-size: 2.2rem;
    }
    #home p {
      font-size: 1.2rem;
    }
    header h1 {
      font-size: 1.4rem;
    }
  }
</style>
</head>
<body>
<header>
  <h1>Food Monster</h1>
  <nav aria-label="Main Navigation">
    <a href="#home" class="active" tabindex="0">Home</a>
    <a href="#menu" tabindex="0">Menu</a>
    <a href="#administration" tabindex="0">Administration</a>
    <a href="#contact" tabindex="0">Contact Us</a>
  </nav>
</header>

<main>
  <section id="home" tabindex="0" aria-label="Home banner section">
    <h2>Welcome to Food Monster</h2>
    <p>Experience the finest flavors crafted with love and passion. Discover your new favorite meal today.</p>
    <button onclick="location.href='#menu'">Explore Our Menu</button>
  </section>
  
  <section id="menu" tabindex="0" aria-label="Food menu section">
    <h2>Our Menu</h2>
    <div class="menu-grid">
      <article class="menu-item" tabindex="0" aria-label="Spaghetti Carbonara">
        <img src="c:\Users\admin\Downloads\noodles.jpg" alt="Spaghetti Carbonara" />
        <div class="menu-item-content">
          <h3>Spaghetti Carbonara</h3>
          <p>Classic Italian pasta with creamy egg-based sauce, pancetta, and Parmesan cheese.</p>
          <div class="price">$14</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Margherita Pizza">
        <img src="c:\Users\admin\Downloads\pizza.jpg" alt="Margherita Pizza" />
        <div class="menu-item-content">
          <h3>Margherita Pizza</h3>
          <p>Wood-fired pizza topped with fresh mozzarella, tomatoes, and basil leaves.</p>
          <div class="price">$12</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Grilled Salmon">
        <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=500&q=80" alt="Grilled Salmon" />
        <div class="menu-item-content">
          <h3>Grilled Salmon</h3>
          <p>Fresh salmon fillet grilled to perfection, served with seasonal vegetables.</p>
          <div class="price">$18</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Caesar Salad">
        <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?auto=format&fit=crop&w=500&q=80" alt="Caesar Salad" />
        <div class="menu-item-content">
          <h3>Caesar Salad</h3>
          <p>Crisp romaine lettuce with Caesar dressing, croutons, and shaved Parmesan.</p>
          <div class="price">$9</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Beef Burger">
        <img src="https://images.unsplash.com/photo-1550547660-d9450f859349?auto=format&fit=crop&w=500&q=80" alt="Beef Burger" />
        <div class="menu-item-content">
          <h3>Beef Burger</h3>
          <p>Juicy beef patty with cheddar cheese, lettuce, tomato, and special sauce.</p>
          <div class="price">$15</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Chicken Tikka Masala">
        <img src="c:\Users\admin\Downloads\chicken tikka.jpeg" alt="Chicken Tikka Masala" />
        <div class="menu-item-content">
          <h3>Chicken Tikka Masala</h3>
          <p>Spiced chicken chunks simmered in creamy tomato-based curry sauce.</p>
          <div class="price">$16</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Vegetable Stir Fry">
        <img src="https://images.unsplash.com/photo-1504754524776-8f4f37790ca0?auto=format&fit=crop&w=500&q=80" alt="Vegetable Stir Fry" />
        <div class="menu-item-content">
          <h3>Vegetable Stir Fry</h3>
          <p>Assorted fresh vegetables sautéed in a tangy soy and ginger sauce.</p>
          <div class="price">$11</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Chocolate Lava Cake">
        <img src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=500&q=80" alt="Chocolate Lava Cake" />
        <div class="menu-item-content">
          <h3>Chocolate Lava Cake</h3>
          <p>Warm chocolate cake with a gooey molten center, served with vanilla ice cream.</p>
          <div class="price">$8</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Shrimp Scampi">
        <img src="https://images.unsplash.com/photo-1600891964599-f61ba0e24092?auto=format&fit=crop&w=500&q=80" alt="Shrimp Scampi" />
        <div class="menu-item-content">
          <h3>Shrimp Scampi</h3>
          <p>Succulent shrimp sautéed in garlic butter sauce, served with linguine pasta.</p>
          <div class="price">$17</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="French Onion Soup">
        <img src="c:\Users\admin\Downloads\onion soup.jpg" alt="French Onion Soup" />
        <div class="menu-item-content">
          <h3>French Onion Soup</h3>
          <p>Rich beef broth with caramelized onions, topped with melted Gruyère cheese.</p>
          <div class="price">$10</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Tandoori Chicken">
        <img src="c:\Users\admin\Downloads\tandoori.jpg" alt="Tandoori Chicken" />
        <div class="menu-item-content">
          <h3>Tandoori Chicken</h3>
          <p>Spicy marinated chicken roasted in traditional clay oven for smoky flavor.</p>
          <div class="price">$16</div>
        </div>
      </article>
      <article class="menu-item" tabindex="0" aria-label="Greek Salad">
        <img src="https://images.unsplash.com/photo-1568605114967-8130f3a36994?auto=format&fit=crop&w=500&q=80" alt="Greek Salad" />
        <div class="menu-item-content">
          <h3>Greek Salad</h3>
          <p>Fresh cucumbers, tomatoes, olives, feta cheese, and red onions in lemon dressing.</p>
          <div class="price">$10</div>
        </div>
      </article>
    </div>
  </section>

  <section id="administration" tabindex="0" aria-label="Administration team section">
    <h2>Our Team</h2>
    <div class="admin-grid">
      <article class="admin-member" tabindex="0" aria-label="Alice Johnson, Head Chef">
        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Alice Johnson" />
        <h3>Alice Johnson</h3>
        <p>Head Chef</p>
      </article>
      <article class="admin-member" tabindex="0" aria-label="Michael Smith, Restaurant Manager">
        <img src="https://randomuser.me/api/portraits/men/45.jpg" alt="Michael Smith" />
        <h3>Michael Smith</h3>
        <p>Restaurant Manager</p>
      </article>
      <article class="admin-member" tabindex="0" aria-label="Sophia Lee, Pastry Chef">
        <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Sophia Lee" />
        <h3>Sophia Lee</h3>
        <p>Pastry Chef</p>
      </article>
      <article class="admin-member" tabindex="0" aria-label="David Kim, Sous Chef">
        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="David Kim" />
        <h3>David Kim</h3>
        <p>Sous Chef</p>
      </article>
      <article class="admin-member" tabindex="0" aria-label="Emily Davis, Sommelier">
        <img src="https://randomuser.me/api/portraits/women/25.jpg" alt="Emily Davis" />
        <h3>Emily Davis</h3>
        <p>Sommelier</p>
      </article>
      <article class="admin-member" tabindex="0" aria-label="James Wilson, Head Waiter">
        <img src="https://randomuser.me/api/portraits/men/15.jpg" alt="James Wilson" />
        <h3>James Wilson</h3>
        <p>Head Waiter</p>
      </article>
    </div>
  </section>

  <section id="contact" tabindex="0" aria-label="Contact information section">
    <h2>Contact Us</h2>
    <div class="contact-info">
      <p><strong>Address:</strong> 123 ,T.Nagar,chennai - 28</p>
      <p><strong>Phone:</strong> +91 9876543210</p>
      <p><strong>Email:</strong> contact@foodmonster.com</p>
    </div>
  </section>
</main>

<footer>
  &copy; 2025 Food Monster | Designed by Madhesh I
</footer>

<script>
  // Highlight active nav link on scroll
  const sections = document.querySelectorAll('main section');
  const navLinks = document.querySelectorAll('nav a');

  window.addEventListener('scroll', () => {
    let current = '';
    let scrollY = window.pageYOffset;

    sections.forEach(section => {
      const sectionTop = section.offsetTop - 80;
      if(scrollY >= sectionTop){
        current = section.getAttribute('id');
      }
    });

    navLinks.forEach(link => {
      link.classList.remove('active');
      if(link.getAttribute('href').substring(1) === current){
        link.classList.add('active');
      }
    });
  });
</script>
</body>
</html>


```

## OUTPUT:
![alt text](<Screenshot 2025-05-18 185501.png>)
![alt text](<Screenshot 2025-05-18 185513.png>)
![alt text](<Screenshot 2025-05-18 185525.png>)
## RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
