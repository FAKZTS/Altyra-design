<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CreativeStudio | Agência de Design Gráfico</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #ff3366;
            --dark: #333;
            --light: #f5f5f5;
            --accent: #00c6ff;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--primary);
        }

        .logo span {
            color: var(--dark);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav li {
            margin-left: 30px;
        }

        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary);
        }

        .button {
            background-color: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            transition: background-color 0.3s;
        }

        .button:hover {
            background-color: #e61a54;
            color: white;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            padding-top: 80px;
            background: linear-gradient(135deg, rgba(255, 51, 102, 0.05) 0%, rgba(0, 198, 255, 0.05) 100%);
        }

        .hero-content {
            width: 50%;
            animation: fadeIn 1s ease-in;
        }

        .hero-image {
            width: 50%;
            text-align: center;
            animation: slideIn 1s ease-in;
        }

        .hero-image img {
            max-width: 100%;
            height: auto;
        }

        h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--dark);
        }

        h1 span {
            color: var(--primary);
        }

        p {
            margin-bottom: 30px;
            font-size: 18px;
        }

        .services {
            padding: 100px 0;
            background-color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            font-size: 36px;
            color: var(--dark);
        }

        .section-title span {
            color: var(--primary);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }

        .service-item {
            background-color: var(--light);
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s;
        }

        .service-item:hover {
            transform: translateY(-10px);
        }

        .service-icon {
            font-size: 40px;
            margin-bottom: 20px;
            color: var(--primary);
        }

        h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }

        .portfolio {
            padding: 100px 0;
            background-color: var(--light);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 300px;
        }

        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 51, 102, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.5s;
            color: white;
            padding: 20px;
            text-align: center;
        }

        .portfolio-item:hover img {
            transform: scale(1.1);
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .team {
            padding: 100px 0;
            background-color: white;
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .team-member {
            text-align: center;
        }

        .team-photo {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;
            margin: 0 auto 20px;
            border: 5px solid var(--light);
        }

        .team-photo img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .social-links {
            display: flex;
            justify-content: center;
            margin-top: 15px;
            gap: 10px;
        }

        .social-link {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: var(--light);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--dark);
            text-decoration: none;
            transition: background-color 0.3s;
        }

        .social-link:hover {
            background-color: var(--primary);
            color: white;
        }

        .contact {
            padding: 100px 0;
            background: linear-gradient(135deg, rgba(255, 51, 102, 0.05) 0%, rgba(0, 198, 255, 0.05) 100%);
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
        }

        .contact-info h3 {
            margin-bottom: 30px;
        }

        .contact-info p {
            margin-bottom: 15px;
        }

        .contact-form .form-group {
            margin-bottom: 20px;
        }

        .contact-form label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }

        .contact-form textarea {
            height: 150px;
        }

        .contact-form button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }

        .contact-form button:hover {
            background-color: #e61a54;
        }

        footer {
            background-color: var(--dark);
            color: white;
            padding: 50px 0 20px;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h4::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary);
        }

        .footer-col ul {
            list
