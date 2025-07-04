---
layout: default
---
<div class="profile-container">
  <img src="/images/avatar/profile.jpeg" alt="Lucas Wiktorowicz" class="avatar">
  <div>
    <h1>Hello 👋 <br>I'm Lucas Wiktorowicz</h1>
  </div>
</div>
<br>
<hr>
### **I'm a certified emerging IT specialist passionate about network solutions and IT security.**

#### Current goals: 

* completing CCNA 200-301 course by Jeremy's IT lab
* passing CCNA certification
* progression through TryHackMe
* playing with Homelab
* writing blog posts

#### Currently reading: *"Acing the CCNA exam"* by Jeremy McDowell
#### Motto: *"Endure, in enduring grow strong"* Dak'kon - *Planescape Torment*

<hr>
#### **Most recent blog post:**
{% assign latest_post = site.posts | first %}
{% if latest_post %}
  <div style="margin: 20px 0; padding: 15px; border: 1px solid #ddd; border-radius: 5px;">
    <a href="{{ latest_post.url }}" style="text-decoration: none; color: inherit;">
      <div style="display: flex; align-items: center;">
        {% if latest_post.image %}
          <img src="{{ latest_post.image }}" alt="{{ latest_post.title }}" style="width: 120px; height: auto; object-fit: cover; margin-right: 20px;">
        {% endif %}
        <div>
          <h2 style="margin: 0;">{{ latest_post.title }}</h2>
          <p style="font-size: 0.9em; color: #666;">{{ latest_post.date | date: "%B %d, %Y" }}</p>
          <p style="font-size: 0.9em; color: #666;">{{ latest_post.excerpt }}</p>
        </div>
      </div>
    </a>
  </div>
{% endif %}
<hr>
<div align="center">
  <img src="./images/logos/Security+-svg.svg?sanitize=true" alt="Logo" class="logo">
  <img src="./images/logos/Network+-svg.svg?sanitize=true" alt="Logo" class="logo">
  <img src="./images/logos/A+-svg.svg?sanitize=true" alt="Logo" class="logo">
  <img src="./images/logos/microsoft-certified-fundamentals-badge.svg?sanitize=true" alt="Logo" class="logo">
</div>
