<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Houses Engineering</title>
    <style>
        /* Reset and Base Styles */
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --text: #333;
            --text-light: #7f8c8d;
            --max-width: 1200px;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: #f9f9f9;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        .container {
            width: 100%;
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 0 20px;
        }

        .btn {
            display: inline-block;
            padding: 12px 24px;
            background-color: var(--secondary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 14px;
        }

        .btn:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--secondary);
            color: var(--secondary);
        }

        .btn-outline:hover {
            background-color: var(--secondary);
            color: white;
        }

        .section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 40px;
            color: var(--primary);
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--secondary);
            margin: 15px auto;
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: white;
            box-shadow: var(--shadow);
            z-index: 1000;
            transition: var(--transition);
        }

        header.scrolled {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
        }

        .logo span {
            color: var(--secondary);
        }

        .nav-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--primary);
        }

        .nav-menu {
            display: flex;
             
            gap: 30px;
            
        }

        .nav-link {
            font-weight: 600;
            color: var(--primary);
            transition: var(--transition);
            position: relative;
        }

        .nav-link:hover {
            color: var(--secondary);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--secondary);
            transition: var(--transition);
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: white;
            display: flex;
            align-items: center;
            text-align: center;
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 20px;
            animation: fadeInDown 1s ease;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .hero-btns {
            display: flex;
            gap: 20px;
            justify-content: center;
            animation: fadeInUp 1s ease 0.6s both;
        }

        /* Features Section */
        .features {
            background-color: white;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: white;
            border-radius: 8px;
            padding: 30px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        /* About Section */
        .about {
            background-color: var(--light);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .about-text p {
            margin-bottom: 20px;
        }

        .about-image {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .about-image img {
            display: block;
            transition: var(--transition);
        }

        .about-image:hover img {
            transform: scale(1.05);
        }

        /* Services Section */
        .services {
            background-color: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-image {
            height: 200px;
            overflow: hidden;
        }

        .service-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .service-card:hover .service-image img {
            transform: scale(1.1);
        }

        .service-content {
            padding: 20px;
        }

        .service-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        /* Testimonials Section */
        .testimonials {
            background-color: var(--light);
        }

        .testimonials-slider {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        .testimonial {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            text-align: center;
            display: none;
        }

        .testimonial.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .testimonial-text {
            font-size: 1.2rem;
            font-style: italic;
            margin-bottom: 20px;
            color: var(--text);
        }

        .testimonial-author {
            font-weight: 600;
            color: var(--primary);
        }

        .testimonial-role {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .slider-controls {
            display: flex;
            justify-content: center;
            margin-top: 30px;
            gap: 10px;
        }

        .slider-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: #bdc3c7;
            cursor: pointer;
            transition: var(--transition);
        }

        .slider-dot.active {
            background-color: var(--secondary);
        }

        /* Contact Section */
        .contact {
            background-color: white;
        }

        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .contact-details {
            margin-bottom: 30px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 15px;
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--secondary);
            margin-right: 15px;
            margin-top: 5px;
        }

        .contact-form .form-group {
            margin-bottom: 20px;
        }

        .contact-form label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-family: inherit;
            transition: var(--transition);
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--secondary);
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }

        .contact-form textarea {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 20px;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .footer-logo span {
            color: var(--secondary);
        }

        .footer-about p {
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
        }

        .footer-links h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--secondary);
        }

        .footer-links ul li {
            margin-bottom: 10px;
        }

        .footer-links a {
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }

        .footer-newsletter p {
            margin-bottom: 20px;
        }

        .newsletter-form {
            display: flex;
        }

        .newsletter-form input {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 4px 0 0 4px;
            font-family: inherit;
        }

        .newsletter-form button {
            padding: 0 20px;
            background-color: var(--secondary);
            color: white;
            border: none;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            transition: var(--transition);
        }

        .newsletter-form button:hover {
            background-color: #2980b9;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }

        /* Other Pages */
        .page-header {
            height: 300px;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: white;
            display: flex;
            align-items: center;
            text-align: center;
            padding-top: 80px;
        }

        .page-header h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .breadcrumb {
            display: flex;
            justify-content: center;
            gap: 10px;
        }

        .breadcrumb a {
            transition: var(--transition);
        }

        .breadcrumb a:hover {
            color: var(--secondary);
        }

        .breadcrumb span {
            color: var(--secondary);
        }

        /* Services Page */
        .services-page {
            padding: 80px 0;
        }

        .services-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-item {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .service-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-item-image {
            height: 200px;
            overflow: hidden;
        }

        .service-item-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .service-item:hover .service-item-image img {
            transform: scale(1.1);
        }

        .service-item-content {
            padding: 20px;
        }

        .service-item-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .service-item-excerpt {
            margin-bottom: 20px;
            color: var(--text-light);
        }

        /* Service Detail Page */
        .service-detail {
            padding: 80px 0;
        }

        .service-detail-container {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 50px;
        }

        .service-detail-content h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .service-detail-content h3 {
            font-size: 1.5rem;
            margin: 30px 0 15px;
            color: var(--primary);
        }

        .service-detail-content p {
            margin-bottom: 20px;
        }

        .service-detail-content ul {
            margin-bottom: 30px;
            padding-left: 20px;
        }

        .service-detail-content li {
            margin-bottom: 10px;
            list-style-type: disc;
        }

        .service-sidebar {
            background-color: var(--light);
            padding: 30px;
            border-radius: 8px;
            height: fit-content;
        }

        .sidebar-widget {
            margin-bottom: 30px;
        }

        .sidebar-widget h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary);
            padding-bottom: 10px;
            border-bottom: 2px solid var(--secondary);
        }

        .service-list-widget li {
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #ddd;
        }

        .service-list-widget a {
            transition: var(--transition);
            display: block;
        }

        .service-list-widget a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }

        .contact-widget p {
            margin-bottom: 20px;
        }

        /* Projects Page */
        .projects-page {
            padding: 80px 0;
        }

        .projects-filter {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 8px 20px;
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
        }

        .filter-btn.active,
        .filter-btn:hover {
            background-color: var(--secondary);
            color: white;
            border-color: var(--secondary);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .project-image {
            height: 250px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-content {
            padding: 20px;
        }

        .project-category {
            display: inline-block;
            padding: 5px 10px;
            background-color: var(--light);
            color: var(--secondary);
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .project-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .project-excerpt {
            margin-bottom: 20px;
            color: var(--text-light);
        }

        /* Project Detail Page */
        .project-detail {
            padding: 80px 0;
        }

        .project-detail-container {
            max-width: 900px;
            margin: 0 auto;
        }

        .project-detail-header {
            margin-bottom: 40px;
        }

        .project-detail-title {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .project-meta {
            display: flex;
            gap: 20px;
            margin-bottom: 20px;
            color: var(--text-light);
        }

        .project-meta span {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .project-detail-image {
            margin-bottom: 40px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .project-detail-image img {
            display: block;
            width: 100%;
            height: auto;
        }

        .project-detail-content h2 {
            font-size: 1.8rem;
            margin: 30px 0 15px;
            color: var(--primary);
        }

        .project-detail-content p {
            margin-bottom: 20px;
        }

        .project-gallery {
            margin: 50px 0;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
        }

        .gallery-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .gallery-item img {
            display: block;
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        /* About Page */
        .about-page {
            padding: 80px 0;
        }

        .about-page-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
            margin-bottom: 60px;
        }

        .about-page-text h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .about-page-image {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .about-page-image img {
            display: block;
            transition: var(--transition);
        }

        .about-page-image:hover img {
            transform: scale(1.05);
        }

        .team-section h2 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 40px;
            color: var(--primary);
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .team-member {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
        }

        .team-member:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .team-member-image {
            height: 250px;
            overflow: hidden;
        }

        .team-member-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .team-member:hover .team-member-image img {
            transform: scale(1.1);
        }

        .team-member-info {
            padding: 20px;
        }

        .team-member-name {
            font-size: 1.3rem;
            margin-bottom: 5px;
            color: var(--primary);
        }

        .team-member-position {
            color: var(--secondary);
            margin-bottom: 15px;
            font-weight: 600;
        }

        .team-member-bio {
            margin-bottom: 20px;
            color: var(--text-light);
        }

        .team-social {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .team-social a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background-color: var(--light);
            color: var(--primary);
            transition: var(--transition);
        }

        .team-social a:hover {
            background-color: var(--secondary);
            color: white;
        }

        /* Legal Page */
        .legal-page {
            padding: 80px 0;
        }

        .legal-container {
            max-width: 900px;
            margin: 0 auto;
            background-color: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: var(--shadow);
        }

        .legal-container h1 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: var(--primary);
        }

        .legal-container h2 {
            font-size: 1.8rem;
            margin: 30px 0 15px;
            color: var(--primary);
        }

        .legal-container p {
            margin-bottom: 20px;
        }

        .legal-container ul {
            margin-bottom: 30px;
            padding-left: 20px;
        }

        .legal-container li {
            margin-bottom: 10px;
            list-style-type: disc;
        }

        /* Modal */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal.open {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            position: relative;
            max-width: 90%;
            max-height: 90%;
        }

        .modal-content img {
            max-width: 100%;
            max-height: 80vh;
            display: block;
            border-radius: 8px;
        }

        .modal-close {
            position: absolute;
            top: -40px;
            right: 0;
            background: none;
            border: none;
            color: white;
            font-size: 2rem;
            cursor: pointer;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 992px) {
            .about-content,
            .contact-container,
            .service-detail-container,
            .about-page-content {
                grid-template-columns: 1fr;
            }

            .about-image,
            .about-page-image {
                order: -1;
            }

            .service-sidebar {
                margin-top: 50px;
            }
        }

        @media (max-width: 768px) {
            .nav-toggle {
                display: block;
            }

            .nav-menu {
                position: fixed;
                top: 80px;
                left: 0;
                width: 100%;
                background-color: white;
                flex-direction: column;
                align-items: center;
                padding: 20px 0;
                box-shadow: var(--shadow);
                transform: translateY(-150%);
                transition: var(--transition);
                z-index: 999;
            }

            .nav-menu.open {
                transform: translateY(0);
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .project-detail-title {
                font-size: 2rem;
            }

            .project-meta {
                flex-direction: column;
                gap: 10px;
            }
        }

        @media (max-width: 576px) {
            .hero-btns {
                flex-direction: column;
            }

            .hero-title {
                font-size: 2rem;
            }

            .section {
                padding: 60px 0;
            }

            .projects-grid,
            .gallery-grid {
                grid-template-columns: 1fr;
            }

            .legal-container {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header Component -->
    <header id="header">
        <div class="container header-container">
            <a href="image.png" class="logo">Smart<span>Houses</span></a>
            <button class="nav-toggle" id="navToggle">
                <i class="fas fa-bars"></i>
            </button>
            <nav class="nav-menu" id="navMenu">
                <a href="index.html" class="nav-link">Home</a>
                <a href="services.html" class="nav-link">Services</a>
                <a href="projects.html" class="nav-link">Projects</a>
                <a href="about.html" class="nav-link">About Us</a>
                <a href="#contact" class="nav-link">Contact</a>
            </nav>
        </div>
    </header>

    <!-- Main Content (will be replaced based on page) -->
    <main id="main-content">
        <!-- Default content (Home page) -->
        <section class="hero" id="home">
            <div class="hero-content">
                <h1 class="hero-title">Smart Solutions for Modern Living</h1>
                <p class="hero-subtitle">We design and build intelligent homes that combine comfort, security and energy efficiency</p>
                <div class="hero-btns">
                    <a href="services.html" class="btn">Our Services</a>
                    <a href="#contact" class="btn btn-outline">Get a Quote</a>
                </div>
            </div>
        </section>

        <section class="section features" id="features">
            <div class="container">
                <h2 class="section-title">Why Choose Us</h2>
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-home"></i>
                        </div>
                        <h3 class="feature-title">Smart Home Integration</h3>
                        <p>Seamlessly connect all your home systems for ultimate control and convenience.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-shield-alt"></i>
                        </div>
                        <h3 class="feature-title">Advanced Security</h3>
                        <p>State-of-the-art security systems to protect your home and family 24/7.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-leaf"></i>
                        </div>
                        <h3 class="feature-title">Energy Efficiency</h3>
                        <p>Reduce your carbon footprint and save money with our eco-friendly solutions.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="section about" id="about">
            <div class="container">
                <div class="about-content">
                    <div class="about-text">
                        <h2>About Smart Houses Engineering</h2>
                        <p>Founded in 2010, Smart Houses Engineering has been at the forefront of home automation and intelligent building solutions. Our team of certified engineers and designers work together to create homes that are not just smart, but intuitive.</p>
                        <p>We believe technology should enhance your living experience without complicating it. That's why we focus on user-friendly solutions that adapt to your lifestyle.</p>
                        <a href="about.html" class="btn">Learn More</a>
                    </div>
                    <div class="about-image">
                        <img src="https://images.unsplash.com/photo-1605276374104-dee2a0ed3cd6?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart home control panel">
                    </div>
                </div>
            </div>
        </section>

        <section class="section services" id="services">
            <div class="container">
                <h2 class="section-title">Our Services</h2>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-image">
                            <img src="https://images.unsplash.com/photo-1558002038-1055907df827?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Home automation">
                        </div>
                        <div class="service-content">
                            <h3 class="service-title">Home Automation</h3>
                            <p>Control lighting, climate, entertainment and more from anywhere with our comprehensive automation systems.</p>
                            <a href="service-details.html" class="btn btn-outline">Details</a>
                        </div>
                    </div>
                    <div class="service-card">
                        <div class="service-image">
                            <img src="https://images.unsplash.com/photo-1563986768609-322da13575f3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Security systems">
                        </div>
                        <div class="service-content">
                            <h3 class="service-title">Security Systems</h3>
                            <p>Advanced surveillance, access control and alarm systems tailored to your specific security needs.</p>
                            <a href="service-details.html" class="btn btn-outline">Details</a>
                        </div>
                    </div>
                    <div class="service-card">
                        <div class="service-image">
                            <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Energy management">
                        </div>
                        <div class="service-content">
                            <h3 class="service-title">Energy Management</h3>
                            <p>Smart solutions to monitor and optimize your home's energy consumption for maximum efficiency.</p>
                            <a href="service-details.html" class="btn btn-outline">Details</a>
                        </div>
                    </div>
                </div>
                <div class="text-center" style="margin-top: 40px;">
                    <a href="services.html" class="btn">View All Services</a>
                </div>
            </div>
        </section>

        <section class="section testimonials" id="testimonials">
            <div class="container">
                <h2 class="section-title">What Our Clients Say</h2>
                <div class="testimonials-slider">
                    <div class="testimonial active">
                        <p class="testimonial-text">"Smart Houses Engineering transformed our home into a futuristic living space that's incredibly easy to use. Their attention to detail and customer service is unmatched."</p>
                        <p class="testimonial-author">Sarah Johnson</p>
                        <p class="testimonial-role">Homeowner, Boston</p>
                    </div>
                    <div class="testimonial">
                        <p class="testimonial-text">"The energy savings alone have paid for the system in just two years. We couldn't be happier with the smart solutions provided by this talented team."</p>
                        <p class="testimonial-author">Michael Chen</p>
                        <p class="testimonial-role">Business Owner, New York</p>
                    </div>
                    <div class="testimonial">
                        <p class="testimonial-text">"From design to installation, the entire process was seamless. Our smart home works perfectly and has significantly improved our quality of life."</p>
                        <p class="testimonial-author">Emily Rodriguez</p>
                        <p class="testimonial-role">Architect, Chicago</p>
                    </div>
                    <div class="slider-controls">
                        <div class="slider-dot active" data-slide="0"></div>
                        <div class="slider-dot" data-slide="1"></div>
                        <div class="slider-dot" data-slide="2"></div>
                    </div>
                </div>
            </div>
        </section>

        <section class="section projects" id="projects">
            <div class="container">
                <h2 class="section-title">Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Modern smart home">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Full Automation</span>
                            <h3 class="project-title">Lakeside Smart Villa</h3>
                            <p class="project-excerpt">Complete home automation system with integrated security and energy management for a luxury lakeside property.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart apartment">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Security System</span>
                            <h3 class="project-title">Downtown Penthouse</h3>
                            <p class="project-excerpt">Custom security solution with facial recognition and remote monitoring for a high-end urban apartment.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart office">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Energy Management</span>
                            <h3 class="project-title">Corporate Headquarters</h3>
                            <p class="project-excerpt">Smart lighting and climate control system that reduced energy costs by 40% for a tech company's offices.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                </div>
                <div class="text-center" style="margin-top: 40px;">
                    <a href="projects.html" class="btn">View All Projects</a>
                </div>
            </div>
        </section>

        <section class="section contact" id="contact">
            <div class="container">
                <h2 class="section-title">Get In Touch</h2>
                <div class="contact-container">
                    <div class="contact-info">
                        <h3>Contact Information</h3>
                        <div class="contact-details">
                            <div class="contact-item">
                                <span class="contact-icon">
                                    <i class="fas fa-map-marker-alt"></i>
                                </span>
                                <p>123 Smart Street, Tech City, TC 10101</p>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">
                                    <i class="fas fa-phone"></i>
                                </span>
                                <p>+1 (555) 123-4567</p>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">
                                    <i class="fas fa-envelope"></i>
                                </span>
                                <p>info@smarthouses.com</p>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">
                                    <i class="fas fa-clock"></i>
                                </span>
                                <p>Monday - Friday: 9:00 AM - 6:00 PM</p>
                            </div>
                        </div>
                        <div class="contact-social">
                            <h3>Follow Us</h3>
                            <div class="social-links">
                                <a href="#" class="social-link">
                                    <i class="fab fa-facebook-f"></i>
                                </a>
                                <a href="#" class="social-link">
                                    <i class="fab fa-twitter"></i>
                                </a>
                                <a href="#" class="social-link">
                                    <i class="fab fa-instagram"></i>
                                </a>
                                <a href="#" class="social-link">
                                    <i class="fab fa-linkedin-in"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                    <div class="contact-form">
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="name">Your Name</label>
                                <input type="text" id="name" name="name" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Your Email</label>
                                <input type="email" id="email" name="email" required>
                            </div>
                            <div class="form-group">
                                <label for="phone">Phone Number</label>
                                <input type="tel" id="phone" name="phone">
                            </div>
                            <div class="form-group">
                                <label for="service">Service Interested In</label>
                                <select id="service" name="service" class="form-control">
                                    <option value="">Select a service</option>
                                    <option value="automation">Home Automation</option>
                                    <option value="security">Security Systems</option>
                                    <option value="energy">Energy Management</option>
                                    <option value="consultation">Consultation</option>
                                    <option value="other">Other</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="message">Your Message</label>
                                <textarea id="message" name="message" rows="5" required></textarea>
                            </div>
                            <button type="submit" class="btn">Send Message</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer Component -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-about">
                    <div class="footer-logo">Smart<span>Houses</span></div>
                    <p>Creating intelligent living spaces that enhance comfort, security and efficiency through innovative technology solutions.</p>
                    <div class="social-links">
                        <a href="#" class="social-link">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-linkedin-in"></i>
                        </a>
                    </div>
                </div>
                <div class="footer-links">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="index.html">Home</a></li>
                        <li><a href="services.html">Services</a></li>
                        <li><a href="projects.html">Projects</a></li>
                        <li><a href="about.html">About Us</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h3>Services</h3>
                    <ul>
                        <li><a href="service-details.html">Home Automation</a></li>
                        <li><a href="service-details.html">Security Systems</a></li>
                        <li><a href="service-details.html">Energy Management</a></li>
                        <li><a href="service-details.html">Smart Lighting</a></li>
                        <li><a href="service-details.html">Consultation</a></li>
                    </ul>
                </div>
                <div class="footer-newsletter">
                    <h3>Newsletter</h3>
                    <p>Subscribe to our newsletter for the latest updates and smart home tips.</p>
                    <form class="newsletter-form">
                        <input type="email" placeholder="Your Email" required>
                        <button type="submit">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 Smart Houses Engineering. All Rights Reserved. | <a href="privacy.html">Privacy Policy</a> | <a href="terms.html">Terms of Service</a></p>
            </div>
        </div>
    </footer>

    <!-- Services Page (hidden by default) -->
    <div id="services-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>Our Services</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="services.html">Services</a>
                </div>
            </div>
        </section>

        <section class="section services-page">
            <div class="container">
                <div class="services-list">
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1558002038-1055907df827?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Home automation">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Home Automation</h3>
                            <p class="service-item-excerpt">Control every aspect of your home from anywhere in the world with our comprehensive automation solutions.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1563986768609-322da13575f3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Security systems">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Security Systems</h3>
                            <p class="service-item-excerpt">Advanced surveillance, access control and alarm systems tailored to your specific security needs.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Energy management">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Energy Management</h3>
                            <p class="service-item-excerpt">Smart solutions to monitor and optimize your home's energy consumption for maximum efficiency.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1558002038-1055907df827?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart lighting">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Smart Lighting</h3>
                            <p class="service-item-excerpt">Automated lighting systems that adapt to your routines and preferences while saving energy.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1563986768609-322da13575f3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Climate control">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Climate Control</h3>
                            <p class="service-item-excerpt">Intelligent HVAC systems that maintain perfect temperature while minimizing energy waste.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                    <div class="service-item">
                        <div class="service-item-image">
                            <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Consultation">
                        </div>
                        <div class="service-item-content">
                            <h3 class="service-item-title">Consultation</h3>
                            <p class="service-item-excerpt">Expert advice to help you choose the right smart home solutions for your needs and budget.</p>
                            <a href="service-details.html" class="btn btn-outline">Learn More</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Service Details Page (hidden by default) -->
    <div id="service-details-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>Home Automation</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="services.html">Services</a>
                    <span>/</span>
                    <a href="service-details.html">Home Automation</a>
                </div>
            </div>
        </section>

        <section class="section service-detail">
            <div class="container">
                <div class="service-detail-container">
                    <div class="service-detail-content">
                        <h2>Complete Home Automation Solutions</h2>
                        <p>Our home automation systems bring all your smart devices together into one seamless, easy-to-use interface. Control lighting, climate, entertainment, security and more from anywhere in the world using your smartphone, tablet or voice commands.</p>
                        
                        <h3>Key Features</h3>
                        <ul>
                            <li>Centralized control of all smart devices</li>
                            <li>Customizable scenes and routines (Good Morning, Good Night, Away, etc.)</li>
                            <li>Voice control integration with Amazon Alexa, Google Assistant and Apple HomeKit</li>
                            <li>Remote access via secure mobile app</li>
                            <li>Energy monitoring and optimization</li>
                            <li>Seamless integration with third-party devices</li>
                            <li>Professional installation and setup</li>
                            <li>24/7 monitoring and support</li>
                        </ul>

                        <h3>How It Works</h3>
                        <p>Our home automation process begins with a comprehensive consultation to understand your lifestyle, needs and preferences. We then design a customized system that integrates all your devices and creates intuitive control scenarios.</p>
                        <p>After installation, our team provides thorough training to ensure you're comfortable using your new smart home system. We also offer ongoing support and system updates to keep your automation running smoothly.</p>

                        <h3>Compatible Devices</h3>
                        <p>Our systems work with thousands of devices from leading manufacturers including:</p>
                        <ul>
                            <li>Smart lights (Philips Hue, Lutron, LIFX)</li>
                            <li>Thermostats (Nest, Ecobee, Honeywell)</li>
                            <li>Security systems (Ring, Arlo, Nest Cam)</li>
                            <li>Smart locks (August, Yale, Schlage)</li>
                            <li>Entertainment systems (Sonos, Samsung, LG)</li>
                            <li>Voice assistants (Amazon Echo, Google Home, Apple HomePod)</li>
                        </ul>
                    </div>
                    <div class="service-sidebar">
                        <div class="sidebar-widget">
                            <h3>Our Services</h3>
                            <ul class="service-list-widget">
                                <li><a href="service-details.html">Home Automation</a></li>
                                <li><a href="service-details.html">Security Systems</a></li>
                                <li><a href="service-details.html">Energy Management</a></li>
                                <li><a href="service-details.html">Smart Lighting</a></li>
                                <li><a href="service-details.html">Climate Control</a></li>
                                <li><a href="service-details.html">Consultation</a></li>
                            </ul>
                        </div>
                        <div class="sidebar-widget contact-widget">
                            <h3>Get a Free Quote</h3>
                            <p>Interested in our home automation services? Contact us today for a free consultation and quote.</p>
                            <a href="#contact" class="btn">Contact Us</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Projects Page (hidden by default) -->
    <div id="projects-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>Our Projects</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="projects.html">Projects</a>
                </div>
            </div>
        </section>

        <section class="section projects-page">
            <div class="container">
                <div class="projects-filter">
                    <button class="filter-btn active" data-filter="all">All</button>
                    <button class="filter-btn" data-filter="automation">Automation</button>
                    <button class="filter-btn" data-filter="security">Security</button>
                    <button class="filter-btn" data-filter="energy">Energy</button>
                    <button class="filter-btn" data-filter="residential">Residential</button>
                    <button class="filter-btn" data-filter="commercial">Commercial</button>
                </div>
                <div class="projects-grid">
                    <div class="project-card" data-category="automation residential">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Modern smart home">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Full Automation</span>
                            <h3 class="project-title">Lakeside Smart Villa</h3>
                            <p class="project-excerpt">Complete home automation system with integrated security and energy management for a luxury lakeside property.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card" data-category="security residential">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart apartment">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Security System</span>
                            <h3 class="project-title">Downtown Penthouse</h3>
                            <p class="project-excerpt">Custom security solution with facial recognition and remote monitoring for a high-end urban apartment.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card" data-category="energy commercial">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart office">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Energy Management</span>
                            <h3 class="project-title">Corporate Headquarters</h3>
                            <p class="project-excerpt">Smart lighting and climate control system that reduced energy costs by 40% for a tech company's offices.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card" data-category="automation residential">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Modern smart home">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Smart Lighting</span>
                            <h3 class="project-title">Historic Home Retrofit</h3>
                            <p class="project-excerpt">Discreet smart lighting installation in a historic home preserving architectural integrity while adding modern convenience.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card" data-category="security commercial">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart apartment">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Access Control</span>
                            <h3 class="project-title">Medical Facility Security</h3>
                            <p class="project-excerpt">Comprehensive access control system for a sensitive medical research facility with multi-factor authentication.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                    <div class="project-card" data-category="energy residential">
                        <div class="project-image">
                            <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart office">
                        </div>
                        <div class="project-content">
                            <span class="project-category">Solar Integration</span>
                            <h3 class="project-title">Eco Smart Home</h3>
                            <p class="project-excerpt">Full integration of solar panels with smart home system for maximum energy efficiency and self-sufficiency.</p>
                            <a href="project-details.html" class="btn btn-outline">View Project</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Project Details Page (hidden by default) -->
    <div id="project-details-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>Lakeside Smart Villa</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="projects.html">Projects</a>
                    <span>/</span>
                    <a href="project-details.html">Lakeside Smart Villa</a>
                </div>
            </div>
        </section>

        <section class="section project-detail">
            <div class="container">
                <div class="project-detail-container">
                    <div class="project-detail-header">
                        <h2 class="project-detail-title">Lakeside Smart Villa - Complete Home Automation</h2>
                        <div class="project-meta">
                            <span><i class="fas fa-calendar-alt"></i> Completed: June 2022</span>
                            <span><i class="fas fa-map-marker-alt"></i> Lake Tahoe, California</span>
                            <span><i class="fas fa-home"></i> Residential</span>
                        </div>
                    </div>
                    
                    <div class="project-detail-image">
                        <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Lakeside Smart Villa">
                    </div>

                    <div class="project-detail-content">
                        <h2>Project Overview</h2>
                        <p>The Lakeside Smart Villa project involved transforming a luxury lakefront property into a state-of-the-art smart home that combines cutting-edge technology with elegant design. The homeowners wanted a system that would provide convenience, security and energy efficiency while maintaining the home's aesthetic appeal.</p>
                        
                        <h2>Challenges</h2>
                        <p>The main challenges included integrating modern technology into a home with unique architectural features, ensuring reliable operation in a location with variable weather conditions, and creating a system that could be easily operated by both tech-savvy family members and occasional guests.</p>
                        
                        <h2>Our Solution</h2>
                        <p>We designed a comprehensive smart home system centered around a Control4 automation controller with the following components:</p>
                        <ul>
                            <li>Whole-home audio with 12 zones of high-fidelity sound</li>
                            <li>Automated lighting control with circadian rhythm programming</li>
                            <li>Motorized window treatments synchronized with daylight</li>
                            <li>Advanced climate control with room-by-room monitoring</li>
                            <li>4K video distribution to 8 displays throughout the home</li>
                            <li>Integrated security with facial recognition at entry points</li>
                            <li>Energy monitoring and solar panel integration</li>
                            <li>Voice control via Amazon Alexa and touchscreen interfaces</li>
                        </ul>

                        <h2>Results</h2>
                        <p>The completed system provides the homeowners with effortless control over their environment while significantly reducing energy consumption. Key results include:</p>
                        <ul>
                            <li>35% reduction in energy usage through optimized systems</li>
                            <li>Seamless operation of all home systems from a single interface</li>
                            <li>Enhanced security with real-time alerts and remote monitoring</li>
                            <li>Personalized "scenes" that adjust multiple systems with one command</li>
                            <li>Future-proof design allowing for easy upgrades</li>
                        </ul>

                        <div class="project-gallery">
                            <h2>Project Gallery</h2>
                            <div class="gallery-grid">
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart home exterior">
                                </div>
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Control panel">
                                </div>
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Living room automation">
                                </div>
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Security system">
                                </div>
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600566752355-35792bedcfea?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Smart kitchen">
                                </div>
                                <div class="gallery-item">
                                    <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Home theater">
                                </div>
                            </div>
                        </div>

                        <h2>Client Testimonial</h2>
                        <blockquote>
                            <p>"Smart Houses Engineering completely transformed our lake house into a technological marvel that's incredibly easy to use. We can control everything from the lights to the security system with our phones or voice commands. The energy savings alone have been remarkable, and the system has made our home more secure and comfortable than we ever imagined."</p>
                            <cite>- The Thompson Family</cite>
                        </blockquote>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- About Page (hidden by default) -->
    <div id="about-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>About Us</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="about.html">About Us</a>
                </div>
            </div>
        </section>

        <section class="section about-page">
            <div class="container">
                <div class="about-page-content">
                    <div class="about-page-text">
                        <h2>Our Story</h2>
                        <p>Founded in 2010 by a team of engineers and home technology enthusiasts, Smart Houses Engineering began with a simple mission: to make advanced home technology accessible, reliable and truly beneficial for homeowners.</p>
                        <p>What started as a small operation with three employees has grown into a leading provider of smart home solutions with offices in three states and a team of over 50 certified professionals. Our growth has been driven by our commitment to excellence and our passion for creating homes that are not just smart, but intuitive and responsive to their occupants' needs.</p>
                        <p>Over the years, we've installed systems in thousands of homes and commercial properties, constantly refining our approach and staying at the forefront of emerging technologies. Our work has been featured in numerous industry publications and we've received multiple awards for innovation and customer service.</p>
                    </div>
                    <div class="about-page-image">
                        <img src="https://images.unsplash.com/photo-1605276374104-dee2a0ed3cd6?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Our office">
                    </div>
                </div>

                <div class="about-page-content" style="flex-direction: row-reverse;">
                    <div class="about-page-text">
                        <h2>Our Approach</h2>
                        <p>At Smart Houses Engineering, we believe technology should serve people, not the other way around. That's why we take a human-centered approach to every project:</p>
                        <ul>
                            <li><strong>Listen First:</strong> We begin by understanding your lifestyle, needs and preferences.</li>
                            <li><strong>Design Thoughtfully:</strong> Our solutions are customized to your home and how you actually live.</li>
                            <li><strong>Integrate Seamlessly:</strong> We ensure all components work together harmoniously.</li>
                            <li><strong>Simplify Complexity:</strong> Advanced technology made intuitive through thoughtful design.</li>
                            <li><strong>Support Continuously:</strong> Our relationship doesn't end with installation.</li>
                        </ul>
                        <p>This approach has earned us a 98% customer satisfaction rating and numerous repeat clients who trust us with all their smart home needs.</p>
                    </div>
                    <div class="about-page-image">
                        <img src="https://images.unsplash.com/photo-1600880292203-757bb62b4baf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Our team at work">
                    </div>
                </div>

                <div class="team-section">
                    <h2>Meet Our Team</h2>
                    <div class="team-grid">
                        <div class="team-member">
                            <div class="team-member-image">
                                <img src="https://images.unsplash.com/photo-1560250097-0b93528c311a?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="John Smith">
                            </div>
                            <div class="team-member-info">
                                <h3 class="team-member-name">John Smith</h3>
                                <p class="team-member-position">Founder & CEO</p>
                                <p class="team-member-bio">With over 20 years in home technology, John leads our company with a vision for intuitive, human-centered design.</p>
                                <div class="team-social">
                                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                                    <a href="#"><i class="fab fa-twitter"></i></a>
                                </div>
                            </div>
                        </div>
                        <div class="team-member">
                            <div class="team-member-image">
                                <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Sarah Johnson">
                            </div>
                            <div class="team-member-info">
                                <h3 class="team-member-name">Sarah Johnson</h3>
                                <p class="team-member-position">Lead Systems Designer</p>
                                <p class="team-member-bio">Sarah specializes in creating seamless integrations that make complex technology feel simple and natural.</p>
                                <div class="team-social">
                                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                                </div>
                            </div>
                        </div>
                        <div class="team-member">
                            <div class="team-member-image">
                                <img src="https://images.unsplash.com/photo-1562788869-4ed32648eb72?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Michael Chen">
                            </div>
                            <div class="team-member-info">
                                <h3 class="team-member-name">Michael Chen</h3>
                                <p class="team-member-position">Head of Engineering</p>
                                <p class="team-member-bio">Michael ensures all our installations meet the highest standards of quality, reliability and performance.</p>
                                <div class="team-social">
                                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                                    <a href="#"><i class="fab fa-github"></i></a>
                                </div>
                            </div>
                        </div>
                        <div class="team-member">
                            <div class="team-member-image">
                                <img src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Emily Rodriguez">
                            </div>
                            <div class="team-member-info">
                                <h3 class="team-member-name">Emily Rodriguez</h3>
                                <p class="team-member-position">Customer Experience</p>
                                <p class="team-member-bio">Emily leads our training and support programs to ensure clients get the most from their smart homes.</p>
                                <div class="team-social">
                                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                                    <a href="#"><i class="fab fa-twitter"></i></a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Legal Page (hidden by default) -->
    <div id="legal-page" style="display: none;">
        <section class="page-header">
            <div class="container">
                <h1>Privacy Policy</h1>
                <div class="breadcrumb">
                    <a href="index.html">Home</a>
                    <span>/</span>
                    <a href="privacy.html">Privacy Policy</a>
                </div>
            </div>
        </section>

        <section class="section legal-page">
            <div class="container">
                <div class="legal-container">
                    <h1>Privacy Policy</h1>
                    <p>Last updated: January 1, 2023</p>
                    
                    <p>Smart Houses Engineering ("us", "we", or "our") operates the https://www.smarthouses.com website (the "Service").</p>
                    
                    <p>This page informs you of our policies regarding the collection, use, and disclosure of personal data when you use our Service and the choices you have associated with that data.</p>
                    
                    <h2>Information Collection And Use</h2>
                    <p>We collect several different types of information for various purposes to provide and improve our Service to you.</p>
                    
                    <h3>Types of Data Collected</h3>
                    <p><strong>Personal Data</strong></p>
                    <p>While using our Service, we may ask you to provide us with certain personally identifiable information that can be used to contact or identify you ("Personal Data"). Personally identifiable information may include, but is not limited to:</p>
                    <ul>
                        <li>Email address</li>
                        <li>First name and last name</li>
                        <li>Phone number</li>
                        <li>Address, State, Province, ZIP/Postal code, City</li>
                        <li>Cookies and Usage Data</li>
                    </ul>
                    
                    <p><strong>Usage Data</strong></p>
                    <p>We may also collect information how the Service is accessed and used ("Usage Data"). This Usage Data may include information such as your computer's Internet Protocol address (e.g. IP address), browser type, browser version, the pages of our Service that you visit, the time and date of your visit, the time spent on those pages, unique device identifiers and other diagnostic data.</p>
                    
                    <p><strong>Tracking & Cookies Data</strong></p>
                    <p>We use cookies and similar tracking technologies to track the activity on our Service and hold certain information.</p>
                    <p>Cookies are files with small amount of data which may include an anonymous unique identifier. Cookies are sent to your browser from a website and stored on your device. Tracking technologies also used are beacons, tags, and scripts to collect and track information and to improve and analyze our Service.</p>
                    <p>You can instruct your browser to refuse all cookies or to indicate when a cookie is being sent. However, if you do not accept cookies, you may not be able to use some portions of our Service.</p>
                    
                    <h2>Use of Data</h2>
                    <p>Smart Houses Engineering uses the collected data for various purposes:</p>
                    <ul>
                        <li>To provide and maintain the Service</li>
                        <li>To notify you about changes to our Service</li>
                        <li>To allow you to participate in interactive features of our Service when you choose to do so</li>
                        <li>To provide customer care and support</li>
                        <li>To provide analysis or valuable information so that we can improve the Service</li>
                        <li>To monitor the usage of the Service</li>
                        <li>To detect, prevent and address technical issues</li>
                    </ul>
                    
                    <h2>Transfer Of Data</h2>
                    <p>Your information, including Personal Data, may be transferred to — and maintained on — computers located outside of your state, province, country or other governmental jurisdiction where the data protection laws may differ than those from your jurisdiction.</p>
                    <p>If you are located outside United States and choose to provide information to us, please note that we transfer the data, including Personal Data, to United States and process it there.</p>
                    <p>Your consent to this Privacy Policy followed by your submission of such information represents your agreement to that transfer.</p>
                    <p>Smart Houses Engineering will take all steps reasonably necessary to ensure that your data is treated securely and in accordance with this Privacy Policy and no transfer of your Personal Data will take place to an organization or a country unless there are adequate controls in place including the security of your data and other personal information.</p>
                    
                    <h2>Disclosure Of Data</h2>
                    <p><strong>Legal Requirements</strong></p>
                    <p>Smart Houses Engineering may disclose your Personal Data in the good faith belief that such action is necessary to:</p>
                    <ul>
                        <li>To comply with a legal obligation</li>
                        <li>To protect and defend the rights or property of Smart Houses Engineering</li>
                        <li>To prevent or investigate possible wrongdoing in connection with the Service</li>
                        <li>To protect the personal safety of users of the Service or the public</li>
                        <li>To protect against legal liability</li>
                    </ul>
                    
                    <h2>Security Of Data</h2>
                    <p>The security of your data is important to us, but remember that no method of transmission over the Internet, or method of electronic storage is 100% secure. While we strive to use commercially acceptable means to protect your Personal Data, we cannot guarantee its absolute security.</p>
                    
                    <h2>Service Providers</h2>
                    <p>We may employ third party companies and individuals to facilitate our Service ("Service Providers"), to provide the Service on our behalf, to perform Service-related services or to assist us in analyzing how our Service is used.</p>
                    <p>These third parties have access to your Personal Data only to perform these tasks on our behalf and are obligated not to disclose or use it for any other purpose.</p>
                    
                    <h2>Links To Other Sites</h2>
                    <p>Our Service may contain links to other sites that are not operated by us. If you click on a third party link, you will be directed to that third party's site. We strongly advise you to review the Privacy Policy of every site you visit.</p>
                    <p>We have no control over and assume no responsibility for the content, privacy policies or practices of any third party sites or services.</p>
                    
                    <h2>Children's Privacy</h2>
                    <p>Our Service does not address anyone under the age of 18 ("Children").</p>
                    <p>We do not knowingly collect personally identifiable information from anyone under the age of 18. If you are a parent or guardian and you are aware that your Children has provided us with Personal Data, please contact us. If we become aware that we have collected Personal Data from children without verification of parental consent, we take steps to remove that information from our servers.</p>
                    
                    <h2>Changes To This Privacy Policy</h2>
                    <p>We may update our Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page.</p>
                    <p>We will let you know via email and/or a prominent notice on our Service, prior to the change becoming effective and update the "effective date" at the top of this Privacy Policy.</p>
                    <p>You are advised to review this Privacy Policy periodically for any changes. Changes to this Privacy Policy are effective when they are posted on this page.</p>
                    
                    <h2>Contact Us</h2>
                    <p>If you have any questions about this Privacy Policy, please contact us:</p>
                    <ul>
                        <li>By email: privacy@smarthouses.com</li>
                        <li>By phone: +92 123-4567</li>
                        <li>By mail: 123 Smart Street, Tech City, TC 10101</li>
                    </ul>
                </div>
            </div>
        </section>
    </div>

    <!-- Image Modal -->
    <div class="modal" id="imageModal">
        <div class="modal-content">
            <button class="modal-close" id="modalClose">&times;</button>
            <img src="" alt="" id="modalImage">
        </div>
    </div>

    <!-- Font Awesome for icons -->
    <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>

    <!-- Main JavaScript -->
    <script>
        // DOM Elements
        const navToggle = document.getElementById('navToggle');
        const navMenu = document.getElementById('navMenu');
        const header = document.getElementById('header');
        const contactForm = document.getElementById('contactForm');
        const testimonials = document.querySelectorAll('.testimonial');
        const dots = document.querySelectorAll('.slider-dot');
        const filterBtns = document.querySelectorAll('.filter-btn');
        const projectCards = document.querySelectorAll('.project-card');
        const galleryItems = document.querySelectorAll('.gallery-item');
        const modal = document.getElementById('imageModal');
        const modalImage = document.getElementById('modalImage');
        const modalClose = document.getElementById('modalClose');
        const mainContent = document.getElementById('main-content');
        
        // Page content objects
        const pages = {
            home: document.getElementById('main-content').innerHTML,
            services: document.getElementById('services-page').innerHTML,
            serviceDetails: document.getElementById('service-details-page').innerHTML,
            projects: document.getElementById('projects-page').innerHTML,
            projectDetails: document.getElementById('project-details-page').innerHTML,
            about: document.getElementById('about-page').innerHTML,
            legal: document.getElementById('legal-page').innerHTML
        };

        // Current page state
        let currentPage = 'home';
        
        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Set up navigation
            setupNavigation();
            
            // Handle contact form submission
            if (contactForm) {
                contactForm.addEventListener('submit', handleFormSubmit);
            }
            
            // Initialize testimonial slider
            initTestimonialSlider();
            
            // Set up project filtering
            setupProjectFiltering();
            
            // Set up gallery modal
            setupGalleryModal();
            
            // Handle scroll events for header
            window.addEventListener('scroll', handleScroll);
            
            // Handle page routing
            handleRouting();
            
            // Smooth scrolling for anchor links
            setupSmoothScrolling();
        });

        // Navigation functions
        function setupNavigation() {
            navToggle.addEventListener('click', function() {
                navMenu.classList.toggle('open');
            });
            
            // Close mobile menu when clicking a link
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function() {
                    if (navMenu.classList.contains('open')) {
                        navMenu.classList.remove('open');
                    }
                });
            });
        }

        function handleScroll() {
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        }

        // Form handling
        function handleFormSubmit(e) {
            e.preventDefault();
            alert('Thank you for your message! We will get back to you soon.');
            e.target.reset();
        }

        // Testimonial slider
        function initTestimonialSlider() {
            let currentSlide = 0;
            
            function showSlide(index) {
                testimonials.forEach(testimonial => testimonial.classList.remove('active'));
                dots.forEach(dot => dot.classList.remove('active'));
                
                testimonials[index].classList.add('active');
                dots[index].classList.add('active');
                currentSlide = index;
            }
            
            dots.forEach((dot, index) => {
                dot.addEventListener('click', () => showSlide(index));
            });
            
            // Auto-advance slides every 5 seconds
            setInterval(() => {
                currentSlide = (currentSlide + 1) % testimonials.length;
                showSlide(currentSlide);
            }, 5000);
        }

        // Project filtering
        function setupProjectFiltering() {
            filterBtns.forEach(btn => {
                btn.addEventListener('click', function() {
                    const filter = this.dataset.filter;
                    
                    // Update active button
                    filterBtns.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Filter projects
                    projectCards.forEach(card => {
                        if (filter === 'all' || card.dataset.category.includes(filter)) {
                            card.style.display = 'block';
                            setTimeout(() => {
                                card.style.opacity = '1';
                                card.style.transform = 'translateY(0)';
                            }, 50);
                        } else {
                            card.style.opacity = '0';
                            card.style.transform = 'translateY(20px)';
                            setTimeout(() => {
                                card.style.display = 'none';
                            }, 300);
                        }
                    });
                });
            });
        }

        // Gallery modal
        function setupGalleryModal() {
            galleryItems.forEach(item => {
                item.addEventListener('click', function() {
                    const imgSrc = this.querySelector('img').src;
                    modalImage.src = imgSrc;
                    modal.classList.add('open');
                });
            });
            
            modalClose.addEventListener('click', function() {
                modal.classList.remove('open');
            });
            
            modal.addEventListener('click', function(e) {
                if (e.target === modal) {
                    modal.classList.remove('open');
                }
            });
        }

        // Page routing
        function handleRouting() {
            // Check initial URL
            updatePageFromURL();
            
            // Handle back/forward navigation
            window.addEventListener('popstate', updatePageFromURL);
            
            // Intercept link clicks
            document.addEventListener('click', function(e) {
                if (e.target.tagName === 'A' && e.target.href) {
                    const url = new URL(e.target.href);
                    if (url.origin === location.origin) {
                        e.preventDefault();
                        navigateTo(url.pathname);
                    }
                }
            });
        }

        function navigateTo(path) {
            let pageKey = 'home';
            
            if (path.endsWith('services.html')) pageKey = 'services';
            else if (path.endsWith('service-details.html')) pageKey = 'serviceDetails';
            else if (path.endsWith('projects.html')) pageKey = 'projects';
            else if (path.endsWith('project-details.html')) pageKey = 'projectDetails';
            else if (path.endsWith('about.html')) pageKey = 'about';
            else if (path.endsWith('privacy.html') || path.endsWith('terms.html')) pageKey = 'legal';
            
            // Update the page content
            mainContent.innerHTML = pages[pageKey];
            currentPage = pageKey;
            
            // Scroll to top
            window.scrollTo(0, 0);
            
            // Update URL without reload
            history.pushState({}, '', path);
            
            // Reinitialize any page-specific JS
            initializePage();
        }

        function updatePageFromURL() {
            const path = window.location.pathname;
            navigateTo(path);
        }

        function initializePage() {
            // Reinitialize any components that need it
            setupSmoothScrolling();
            
            if (currentPage === 'projects' || currentPage === 'projectDetails') {
                setupProjectFiltering();
                setupGalleryModal();
            }
            
            if (currentPage === 'home') {
                initTestimonialSlider();
            }
        }

        // Smooth scrolling
        function setupSmoothScrolling() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });
        }

        // Simple animation on scroll
        const animateOnScroll = function() {
            const elements = document.querySelectorAll('.feature-card, .service-card, .project-card, .team-member');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.2;
                
                if (elementPosition < screenPosition) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        };

        // Set initial styles for animated elements
        document.querySelectorAll('.feature-card, .service-card, .project-card, .team-member').forEach(element => {
            element.style.opacity = '0';
            element.style.transform = 'translateY(20px)';
            element.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
        });

        // Run animation check on scroll
        window.addEventListener('scroll', animateOnScroll);
        // Run once on page load
        animateOnScroll();
    </script>
</body>
</html>
