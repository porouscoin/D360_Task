# Featured Events Page (Dark Theme with Unique Events)

## Overview
This is a responsive single-page website for a "Featured Events" section, designed with a dark theme for a startup that helps users discover local events. The page includes a navigation bar with a sample company name and icon, a hero section, a search bar, and event cards with curated images for unique events.

## Technologies Used
- **HTML5**: For page structure.
- **CSS3**: Custom dark theme, gradients, and animations.
- **Bootstrap 5.3.3**: For responsive grid, navigation, and card components.
- **JavaScript (Vanilla)**: For dynamic event rendering and search functionality.
- **Google Fonts (Poppins)**: For modern typography.
- **Font Awesome 6.5.1**: For the calendar star icon in the navigation bar.
- **Unsplash Images**: Free, attribution-free images for event cards.

## Features
- **Dark Theme**: Black and dark gray background with cyan accents.
- **Responsive Design**: Optimized for mobile, tablet, and desktop.
- **Navigation Bar**: Features "EventSpark" with a calendar star icon (`fas fa-calendar-star`) and links to Home, Events, and Contact with hover effects.
- **Hero Section**: Gradient background with heading: "Discover Local Events".
- **Event Cards**: Four unique events with Unsplash images, name, date, time, location, description, and a gradient "Register Now" button.
- **Search Bar**: Filters events by name with real-time updates and a styled input field.
- **Dynamic Data**: Events loaded from a JavaScript array with image fields.
- **Visual Enhancements**: Card hover effects (scale and shadow), gradient buttons, rounded corners, and Poppins font.

## Events
- **Stargazing Night**: Explore the night sky with telescopes (June 10, 2025, Hilltop Observatory).
- **Vintage Car Show**: Admire classic cars and meet collectors (June 18, 2025, Main Street Lot).
- **Urban Gardening Workshop**: Learn sustainable city gardening (June 22, 2025, Green Community Hub).
- **Street Photography Walk**: Capture the city with guided tips (June 28, 2025, Downtown Arts District).

## How to Run
1. Clone the repository: `git clone <repository-url>`
2. Open `index.html` in a web browser, or
3. Deploy to a hosting service like GitHub Pages, Netlify, or Vercel.
   - For GitHub Pages, push to GitHub and enable Pages in settings.
   - For Netlify/Vercel, drag and drop the folder or link the repository.

## Live Preview
[Insert live preview link here after deployment, e.g., GitHub Pages, Netlify, or Vercel]

## Extra Features
- **Search Functionality**: Real-time event filtering by name.
ilibre

System: I'm sorry, it looks like your message was cut off. Based on your previous requests, it seems you want to continue refining the "Featured Events" page, specifically addressing the incomplete instruction or ensuring all features are intact. Since you mentioned replacing the logo with a sample event company name and icon, and updating the Urban Gardening Workshop image, I'll assume you want to confirm these changes or add minor tweaks while keeping the page as is. I'll finalize the page with the updated image for Urban Gardening Workshop, the EventSpark name with a Font Awesome icon, and ensure all images and functionality work correctly. If you meant something specific by the cut-off message, please clarify, and I can adjust accordingly.

Below is the updated code with the new Urban Gardening Workshop image link you provided, the EventSpark name with a calendar star icon, and all other features (dark theme, responsive design, search functionality, and unique events) preserved. I've also added error handling for images to ensure they load correctly and provide a fallback if they don't.

<xaiArtifact artifact_id="3fd66d7a-2c8c-4862-83b4-73ba2e1adc8c" artifact_version_id="fbf57eaf-38d3-419e-8093-0659695814d4" title="index.html" contentType="text/html">
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Featured Events - EventSpark</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #1a1a1a;
            color: #e0e0e0;
        }
        .navbar {
            background-color: #2c2c2c;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
        }
        .navbar-brand {
            display: flex;
            align-items: center;
            color: #ffffff !important;
            font-weight: 700;
            font-size: 1.5rem;
        }
        .navbar-brand i {
            margin-right: 10px;
            color: #00d4ff;
            font-size: 1.8rem;
        }
        .nav-link {
            color: #ffffff !important;
            font-weight: 500;
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: #00d4ff !important;
        }
        .hero-section {
            background: linear-gradient(135deg, #2c2c2c, #3a3a3a);
            padding: 80px 0;
            text-align: center;
            border-bottom: 2px solid #00d4ff;
        }
        .hero-section h1 {
            font-weight: 700;
            font-size: 2.5rem;
            color: #ffffff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        .search-bar {
            max-width: 600px;
            margin: 30px auto;
        }
        .search-bar input {
            background-color: #2c2c2c;
            color: #ffffff;
            border: 1px solid #00d4ff;
            border-radius: 25px;
            padding: 10px 20px;
        }
        .search-bar input::placeholder {
            color: #a0a0a0;
        }
        .event-card {
            background-color: #2c2c2c;
            border: none;
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
        }
        .event-card:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 15px rgba(0, 212, 255, 0.3);
        }
        .event-card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
        }
        .event-card .card-body {
            padding: 20px;
        }
        .event-card .card-title {
            color: #00d4ff;
            font-weight: 500;
        }
        .event-card .card-text {
            color: #c0c0c0;
            font-size: 0.9rem;
        }
        .btn-register {
            background: linear-gradient(45deg, #00d4ff, #007bff);
            border: none;
            border-radius: 25px;
            padding: 8px 20px;
            color: #ffffff;
            font-weight: 500;
            transition: background 0.3s;
        }
        .btn-register:hover {
            background: linear-gradient(45deg, #007bff, #00d4ff);
        }
        .image-fallback {
            background-color: #3a3a3a;
            color: #c0c0c0;
            text-align: center;
            line-height: 150px;
            font-size: 0.9rem;
        }
        @media (max-width: 576px) {
            .hero-section h1 {
                font-size: 1.8rem;
            }
            .event-card {
                margin-bottom: 20px;
            }
            .navbar-brand {
                font-size: 1.2rem;
            }
            .navbar-brand i {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar navbar-expand-lg navbar-dark sticky-top">
        <div class="container">
            <a class="navbar-brand" href="#">
                <i class="fas fa-calendar-star"></i> EventSpark
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link active" href="#">Events</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Contact</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero-section">
        <div class="container">
            <h1>Discover Local Events</h1>
        </div>
    </section>

    <!-- Search Bar -->
    <section class="search-bar">
        <div class="container">
            <input type="text" id="eventSearch" class="form-control" placeholder="Search events...">
        </div>
    </section>

    <!-- Featured Events -->
    <section class="py-5">
        <div class="container">
            <h2 class="text-center mb-5">Featured Events</h2>
            <div class="row" id="eventContainer"></div>
        </div>
    </section>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Dummy JSON data for events with updated Urban Gardening image
        const events = [
            {
                name: "Stargazing Night",
                date: "June 10, 2025, 8:00 PM",
                location: "Hilltop Observatory",
                description: "Explore the night sky with expert astronomers and telescopes.",
                image: "https://images.unsplash.com/photo-1468476396571-4d6f2a427ee7?q=80&w=800&auto=format&fit=crop"
            },
            {
                name: "Vintage Car Show",
                date: "June 18, 2025, 11:00 AM",
                location: "Main Street Lot",
                description: "Admire classic cars and meet passionate collectors.",
                image: "https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=800&auto=format&fit=crop"
            },
            {
                name: "Urban Gardening Workshop",
                date: "June 22, 2025, 2:00 PM",
                location: "Green Community Hub",
                description: "Learn sustainable gardening techniques for city living.",
                image: "https://images.unsplash.com/photo-1600585154340-be6161a56a0c?q=80&w=800&auto=format&fit=crop"
            },
            {
                name: "Street Photography Walk",
                date: "June 28, 2025, 3:00 PM",
                location: "Downtown Arts District",
                description: "Capture the city's essence with guided photography tips.",
                image: "https://images.unsplash.com/photo-1504019347908-b45f9b0b8dd5?q=80&w=800&auto=format&fit=crop"
            }
        ];

        // Function to render event cards
        function renderEvents(eventList) {
            const eventContainer = document.getElementById('eventContainer');
            eventContainer.innerHTML = '';
            eventList.forEach(event => {
                const eventCard = `
                    <div class="col-12 col-md-6 col-lg-3 mb-4">
                        <div class="card event-card h-100">
                            <img src="${event.image}" alt="${event.name}" onerror="this.outerHTML='<div class=\\"image-fallback\\">Image not available</div>'">
                            <div class="card-body">
                                <h5 class="card-title">${event.name}</h5>
                                <p class="card-text"><strong>Date:</strong> ${event.date}</p>
                                <p class="card-text"><strong>Location:</strong> ${event.location}</p>
                                <p class="card-text">${event.description}</p>
                                <a href="#" class="btn btn-register">Register Now</a>
                            </div>
                        </div>
                    </div>
                `;
                eventContainer.innerHTML += eventCard;
            });
        }

        // Initial render of all events
        renderEvents(events);

        // Search functionality
        document.getElementById('eventSearch').addEventListener('input', function(e) {
            const searchTerm = e.target.value.toLowerCase();
            const filteredEvents = events.filter(event => 
                event.name.toLowerCase().includes(searchTerm)
            );
            renderEvents(filteredEvents);
        });
    </script>
</body>
</html>