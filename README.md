<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HashtagPro - Professional Hashtag Generator</title>
    <meta name="description" content="Generate 30 unique and relevant hashtags instantly with our professional hashtag generator tool. Perfect for social media marketing and content creators.">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
    <style>
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        .card-shadow {
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        .hashtag-item {
            transition: all 0.3s ease;
        }
        .hashtag-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        .section {
            display: none;
        }
        .section.active {
            display: block;
        }
        .nav-link {
            transition: all 0.3s ease;
        }
        .nav-link:hover {
            transform: translateY(-1px);
        }
        .copy-btn {
            transition: all 0.2s ease;
        }
        .copy-btn:hover {
            background-color: #3b82f6;
        }
        .pulse-animation {
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
    </style>
</head>
<body class="bg-gray-50 font-sans">
    <!-- Navigation -->
    <nav class="bg-white shadow-lg sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0">
                        <h1 class="text-2xl font-bold text-indigo-600">
                            <i class="fas fa-hashtag mr-2"></i>HashtagPro
                        </h1>
                    </div>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#" onclick="showSection('home')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">Home</a>
                    <a href="#" onclick="showSection('about')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">About Us</a>
                    <a href="#" onclick="showSection('contact')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">Contact</a>
                    <a href="#" onclick="showSection('disclaimer')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">Disclaimer</a>
                    <a href="#" onclick="showSection('terms')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">Terms</a>
                    <a href="#" onclick="showSection('privacy')" class="nav-link text-gray-700 hover:text-indigo-600 px-3 py-2 font-medium">Privacy</a>
                </div>
                <div class="md:hidden flex items-center">
                    <button id="mobile-menu-btn" class="text-gray-700 hover:text-indigo-600 focus:outline-none">
                        <i class="fas fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>
        <!-- Mobile menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-t">
            <div class="px-2 pt-2 pb-3 space-y-1">
                <a href="#" onclick="showSection('home')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">Home</a>
                <a href="#" onclick="showSection('about')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">About Us</a>
                <a href="#" onclick="showSection('contact')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">Contact</a>
                <a href="#" onclick="showSection('disclaimer')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">Disclaimer</a>
                <a href="#" onclick="showSection('terms')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">Terms</a>
                <a href="#" onclick="showSection('privacy')" class="block px-3 py-2 text-gray-700 hover:text-indigo-600 font-medium">Privacy</a>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main>
        <!-- Home Section -->
        <section id="home" class="section active">
            <!-- Hero Section -->
            <div class="gradient-bg text-white py-20">
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
                    <h1 class="text-4xl md:text-6xl font-bold mb-6">Professional Hashtag Generator</h1>
                    <p class="text-xl md:text-2xl mb-8 opacity-90">Generate 30 unique and relevant hashtags instantly for your social media content</p>
                    <div class="max-w-2xl mx-auto">
                        <div class="flex flex-col sm:flex-row gap-4">
                            <input 
                                type="text" 
                                id="keyword-input" 
                                placeholder="Enter your keyword..." 
                                class="flex-1 px-6 py-4 text-lg text-gray-800 rounded-lg border-0 focus:outline-none focus:ring-4 focus:ring-white focus:ring-opacity-50"
                            >
                            <button 
                                onclick="generateHashtags()" 
                                class="bg-yellow-500 hover:bg-yellow-600 text-white px-8 py-4 rounded-lg font-semibold text-lg transition duration-300 transform hover:scale-105"
                            >
                                <i class="fas fa-magic mr-2"></i>Generate
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Results Section -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div id="results-section" class="hidden">
                    <div class="text-center mb-12">
                        <h2 class="text-3xl font-bold text-gray-800 mb-4">Your Generated Hashtags</h2>
                        <p class="text-lg text-gray-600">Click any hashtag to copy it to your clipboard</p>
                        <button onclick="copyAllHashtags()" class="mt-4 bg-indigo-600 hover:bg-indigo-700 text-white px-6 py-2 rounded-lg font-medium transition duration-300">
                            <i class="fas fa-copy mr-2"></i>Copy All Hashtags
                        </button>
                    </div>
                    <div id="hashtags-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-4">
                        <!-- Hashtags will be dynamically inserted here -->
                    </div>
                </div>

                <!-- Features Section -->
                <div class="mt-20">
                    <div class="text-center mb-16">
                        <h2 class="text-3xl font-bold text-gray-800 mb-4">Why Choose HashtagPro?</h2>
                        <p class="text-lg text-gray-600">Powerful features designed for content creators and marketers</p>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                        <div class="text-center p-8 bg-white rounded-xl card-shadow">
                            <div class="w-16 h-16 bg-indigo-100 rounded-full flex items-center justify-center mx-auto mb-6">
                                <i class="fas fa-bolt text-2xl text-indigo-600"></i>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-4">Instant Generation</h3>
                            <p class="text-gray-600">Generate 30 unique hashtags in seconds with our advanced algorithm</p>
                        </div>
                        <div class="text-center p-8 bg-white rounded-xl card-shadow">
                            <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-6">
                                <i class="fas fa-mobile-alt text-2xl text-green-600"></i>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-4">Mobile Friendly</h3>
                            <p class="text-gray-600">Fully responsive design that works perfectly on all devices</p>
                        </div>
                        <div class="text-center p-8 bg-white rounded-xl card-shadow">
                            <div class="w-16 h-16 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-6">
                                <i class="fas fa-copy text-2xl text-purple-600"></i>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-4">Easy Copy</h3>
                            <p class="text-gray-600">One-click copy feature to quickly use hashtags across platforms</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Us Section -->
        <section id="about" class="section">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="text-4xl font-bold text-gray-800 mb-6">About HashtagPro</h1>
                        <p class="text-xl text-gray-600">Empowering content creators with intelligent hashtag solutions</p>
                    </div>
                    
                    <div class="bg-white rounded-xl card-shadow p-8 mb-8">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Our Mission</h2>
                        <p class="text-lg text-gray-600 mb-6">
                            At HashtagPro, we believe that great content deserves great visibility. Our mission is to provide content creators, marketers, and businesses with the most effective hashtag generation tools to maximize their social media reach and engagement.
                        </p>
                        <p class="text-lg text-gray-600">
                            We understand the challenges of creating compelling content that stands out in today's crowded digital landscape. That's why we've developed an intelligent hashtag generator that takes the guesswork out of hashtag selection, helping you focus on what you do best – creating amazing content.
                        </p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h3 class="text-xl font-bold text-gray-800 mb-4">
                                <i class="fas fa-lightbulb text-yellow-500 mr-3"></i>Innovation
                            </h3>
                            <p class="text-gray-600">
                                We continuously innovate our algorithms to provide the most relevant and trending hashtags for your content, ensuring maximum visibility and engagement.
                            </p>
                        </div>
                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h3 class="text-xl font-bold text-gray-800 mb-4">
                                <i class="fas fa-users text-blue-500 mr-3"></i>Community
                            </h3>
                            <p class="text-gray-600">
                                We're built by creators, for creators. Our team understands the needs of the digital content community and develops tools that truly make a difference.
                            </p>
                        </div>
                    </div>

                    <div class="bg-gradient-to-r from-indigo-500 to-purple-600 text-white rounded-xl p-8 text-center">
                        <h3 class="text-2xl font-bold mb-4">Join Thousands of Satisfied Users</h3>
                        <p class="text-lg opacity-90 mb-6">
                            Content creators, influencers, and businesses worldwide trust HashtagPro to boost their social media presence.
                        </p>
                        <button onclick="showSection('home')" class="bg-white text-indigo-600 px-8 py-3 rounded-lg font-semibold hover:bg-gray-100 transition duration-300">
                            Get Started Now
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="text-4xl font-bold text-gray-800 mb-6">Contact Us</h1>
                        <p class="text-xl text-gray-600">We'd love to hear from you. Send us a message and we'll respond as soon as possible.</p>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                        <div>
                            <div class="bg-white rounded-xl card-shadow p-8">
                                <h2 class="text-2xl font-bold text-gray-800 mb-6">Get in Touch</h2>
                                <form id="contact-form" class="space-y-6">
                                    <div>
                                        <label class="block text-gray-700 font-medium mb-2">Your Name</label>
                                        <input type="text" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500">
                                    </div>
                                    <div>
                                        <label class="block text-gray-700 font-medium mb-2">Email Address</label>
                                        <input type="email" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500">
                                    </div>
                                    <div>
                                        <label class="block text-gray-700 font-medium mb-2">Subject</label>
                                        <input type="text" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500">
                                    </div>
                                    <div>
                                        <label class="block text-gray-700 font-medium mb-2">Message</label>
                                        <textarea required rows="5" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500"></textarea>
                                    </div>
                                    <button type="submit" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white py-3 rounded-lg font-semibold transition duration-300">
                                        <i class="fas fa-paper-plane mr-2"></i>Send Message
                                    </button>
                                </form>
                            </div>
                        </div>

                        <div class="space-y-8">
                            <div class="bg-white rounded-xl card-shadow p-8">
                                <h3 class="text-xl font-bold text-gray-800 mb-4">
                                    <i class="fas fa-envelope text-indigo-600 mr-3"></i>Email Us
                                </h3>
                                <p class="text-gray-600 mb-2">For general inquiries:</p>
                                <p class="text-indigo-600 font-medium">info@hashtagpro.com</p>
                                <p class="text-gray-600 mb-2 mt-4">For support:</p>
                                <p class="text-indigo-600 font-medium">support@hashtagpro.com</p>
                            </div>

                            <div class="bg-white rounded-xl card-shadow p-8">
                                <h3 class="text-xl font-bold text-gray-800 mb-4">
                                    <i class="fas fa-clock text-green-600 mr-3"></i>Response Time
                                </h3>
                                <p class="text-gray-600">
                                    We typically respond to all inquiries within 24 hours during business days. For urgent matters, please include "URGENT" in your subject line.
                                </p>
                            </div>

                            <div class="bg-white rounded-xl card-shadow p-8">
                                <h3 class="text-xl font-bold text-gray-800 mb-4">
                                    <i class="fas fa-question-circle text-purple-600 mr-3"></i>FAQ
                                </h3>
                                <p class="text-gray-600">
                                    Before contacting us, you might find your answer in our frequently asked questions section. Check our help documentation for quick solutions.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Disclaimer Section -->
        <section id="disclaimer" class="section">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="text-4xl font-bold text-gray-800 mb-6">Disclaimer</h1>
                        <p class="text-xl text-gray-600">Important information about the use of HashtagPro services</p>
                    </div>

                    <div class="bg-white rounded-xl card-shadow p-8 mb-8">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">General Disclaimer</h2>
                        <p class="text-gray-600 mb-4">
                            The information and tools provided by HashtagPro are for general informational and educational purposes only. While we strive to provide accurate and up-to-date hashtag suggestions, we make no representations or warranties of any kind, express or implied, about the completeness, accuracy, reliability, suitability, or availability of the hashtags generated.
                        </p>
                        <p class="text-gray-600">
                            Your use of any hashtags generated by our service is entirely at your own risk. We are not responsible for any outcomes, positive or negative, that may result from using the hashtags suggested by our platform.
                        </p>
                    </div>

                    <div class="bg-white rounded-xl card-shadow p-8 mb-8">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Platform Guidelines</h2>
                        <p class="text-gray-600 mb-4">
                            Different social media platforms have varying guidelines and policies regarding hashtag usage. It is your responsibility to ensure that any hashtags you use comply with the terms of service and community guidelines of the respective platforms.
                        </p>
                        <p class="text-gray-600 mb-4">
                            We recommend reviewing the hashtag policies of each platform before using our generated hashtags, as violations may result in reduced reach, content removal, or account penalties imposed by those platforms.
                        </p>
                    </div>

                    <div class="bg-white rounded-xl card-shadow p-8 mb-8">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Content Responsibility</h2>
                        <p class="text-gray-600 mb-4">
                            Users are solely responsible for the content they create and share using our hashtag suggestions. HashtagPro does not endorse, monitor, or control the content created by users, and we are not responsible for any content that may be inappropriate, offensive, or violate any laws or regulations.
                        </p>
                        <p class="text-gray-600">
                            We encourage all users to use hashtags responsibly and in accordance with applicable laws, regulations, and platform guidelines.
                        </p>
                    </div>

                    <div class="bg-yellow-50 border-l-4 border-yellow-400 p-6 rounded-r-lg">
                        <div class="flex">
                            <div class="flex-shrink-0">
                                <i class="fas fa-exclamation-triangle text-yellow-400 text-xl"></i>
                            </div>
                            <div class="ml-3">
                                <h3 class="text-lg font-medium text-yellow-800">Important Notice</h3>
                                <p class="text-yellow-700 mt-2">
                                    This disclaimer may be updated from time to time. Continued use of our service after any changes indicates your acceptance of the updated disclaimer.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Terms & Conditions Section -->
        <section id="terms" class="section">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="text-4xl font-bold text-gray-800 mb-6">Terms & Conditions</h1>
                        <p class="text-xl text-gray-600">Please read these terms carefully before using our services</p>
                    </div>

                    <div class="space-y-8">
                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">1. Acceptance of Terms</h2>
                            <p class="text-gray-600 mb-4">
                                By accessing and using HashtagPro, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to these Terms and Conditions, please do not use our service.
                            </p>
                            <p class="text-gray-600">
                                These terms apply to all visitors, users, and others who access or use the service.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">2. Use License</h2>
                            <p class="text-gray-600 mb-4">
                                Permission is granted to temporarily use HashtagPro for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                            </p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2">
                                <li>modify or copy the materials</li>
                                <li>use the materials for any commercial purpose or for any public display</li>
                                <li>attempt to reverse engineer any software contained on the website</li>
                                <li>remove any copyright or other proprietary notations from the materials</li>
                            </ul>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">3. Service Availability</h2>
                            <p class="text-gray-600 mb-4">
                                We strive to maintain the availability of our service, but we do not guarantee that the service will be available at all times. The service may be temporarily unavailable due to maintenance, updates, or technical issues.
                            </p>
                            <p class="text-gray-600">
                                We reserve the right to modify, suspend, or discontinue the service at any time without prior notice.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">4. User Responsibilities</h2>
                            <p class="text-gray-600 mb-4">As a user of HashtagPro, you agree to:</p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2">
                                <li>Use the service in compliance with all applicable laws and regulations</li>
                                <li>Not use the service for any unlawful or prohibited activities</li>
                                <li>Respect the intellectual property rights of others</li>
                                <li>Not attempt to interfere with the proper functioning of the service</li>
                            </ul>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">5. Limitation of Liability</h2>
                            <p class="text-gray-600 mb-4">
                                In no event shall HashtagPro or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on HashtagPro, even if HashtagPro or its authorized representative has been notified orally or in writing of the possibility of such damage.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">6. Modifications</h2>
                            <p class="text-gray-600">
                                HashtagPro may revise these terms of service at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Privacy Policy Section -->
        <section id="privacy" class="section">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="text-4xl font-bold text-gray-800 mb-6">Privacy Policy</h1>
                        <p class="text-xl text-gray-600">Your privacy is important to us. Learn how we collect, use, and protect your information.</p>
                    </div>

                    <div class="space-y-8">
                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">Information We Collect</h2>
                            <p class="text-gray-600 mb-4">
                                We collect information you provide directly to us, such as when you use our hashtag generation service or contact us. This may include:
                            </p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2 mb-4">
                                <li>Keywords you enter into our hashtag generator</li>
                                <li>Contact information when you reach out to us</li>
                                <li>Usage data to improve our service</li>
                            </ul>
                            <p class="text-gray-600">
                                We also automatically collect certain information when you use our service, including your IP address, browser type, and usage patterns.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">How We Use Your Information</h2>
                            <p class="text-gray-600 mb-4">We use the information we collect to:</p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2">
                                <li>Provide, maintain, and improve our hashtag generation service</li>
                                <li>Respond to your comments, questions, and customer service requests</li>
                                <li>Monitor and analyze trends and usage patterns</li>
                                <li>Detect, investigate, and prevent fraudulent transactions and other illegal activities</li>
                            </ul>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">Information Sharing</h2>
                            <p class="text-gray-600 mb-4">
                                We do not sell, rent, or share your personal information with third parties except in the following circumstances:
                            </p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2">
                                <li>With your consent</li>
                                <li>To comply with legal obligations</li>
                                <li>To protect our rights and prevent fraud</li>
                                <li>In connection with a merger, sale, or acquisition</li>
                            </ul>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">Data Security</h2>
                            <p class="text-gray-600 mb-4">
                                We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction. However, no method of transmission over the Internet is 100% secure.
                            </p>
                            <p class="text-gray-600">
                                We regularly review our security practices and update them as necessary to maintain the protection of your information.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">Cookies and Tracking</h2>
                            <p class="text-gray-600 mb-4">
                                We use cookies and similar tracking technologies to enhance your experience on our website. Cookies help us remember your preferences and understand how you use our service.
                            </p>
                            <p class="text-gray-600">
                                You can control cookies through your browser settings, but disabling certain cookies may affect the functionality of our service.
                            </p>
                        </div>

                        <div class="bg-white rounded-xl card-shadow p-8">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">Your Rights</h2>
                            <p class="text-gray-600 mb-4">You have the right to:</p>
                            <ul class="list-disc list-inside text-gray-600 space-y-2">
                                <li>Access and update your personal information</li>
                                <li>Request deletion of your personal data</li>
                                <li>Object to the processing of your information</li>
                                <li>Request data portability</li>
                            </ul>
                        </div>

                        <div class="bg-blue-50 border-l-4 border-blue-400 p-6 rounded-r-lg">
                            <div class="flex">
                                <div class="flex-shrink-0">
                                    <i class="fas fa-info-circle text-blue-400 text-xl"></i>
                                </div>
                                <div class="ml-3">
                                    <h3 class="text-lg font-medium text-blue-800">Contact Us</h3>
                                    <p class="text-blue-700 mt-2">
                                        If you have any questions about this Privacy Policy, please contact us at privacy@hashtagpro.com
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div class="col-span-1 md:col-span-2">
                    <h3 class="text-2xl font-bold mb-4">
                        <i class="fas fa-hashtag mr-2"></i>HashtagPro
                    </h3>
                    <p class="text-gray-300 mb-4 max-w-md">
                        Professional hashtag generator tool designed for content creators, marketers, and businesses looking to maximize their social media reach.
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-300 hover:text-white transition duration-300">
                            <i class="fab fa-twitter text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-300 hover:text-white transition duration-300">
                            <i class="fab fa-facebook text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-300 hover:text-white transition duration-300">
                            <i class="fab fa-instagram text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-300 hover:text-white transition duration-300">
                            <i class="fab fa-linkedin text-xl"></i>
                        </a>
                    </div>
                </div>
                <div>
                    <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
                    <ul class="space-y-2">
                        <li><a href="#" onclick="showSection('home')" class="text-gray-300 hover:text-white transition duration-300">Home</a></li>
                        <li><a href="#" onclick="showSection('about')" class="text-gray-300 hover:text-white transition duration-300">About Us</a></li>
                        <li><a href="#" onclick="showSection('contact')" class="text-gray-300 hover:text-white transition duration-300">Contact</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-semibold mb-4">Legal</h4>
                    <ul class="space-y-2">
                        <li><a href="#" onclick="showSection('disclaimer')" class="text-gray-300 hover:text-white transition duration-300">Disclaimer</a></li>
                        <li><a href="#" onclick="showSection('terms')" class="text-gray-300 hover:text-white transition duration-300">Terms & Conditions</a></li>
                        <li><a href="#" onclick="showSection('privacy')" class="text-gray-300 hover:text-white transition duration-300">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-700 mt-8 pt-8 text-center">
                <p class="text-gray-300">© 2024 HashtagPro. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Global variables
        let generatedHashtags = [];

        // Navigation functionality
        function showSection(sectionId) {
            // Hide all sections
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                section.classList.remove('active');
            });

            // Show selected section
            const targetSection = document.getElementById(sectionId);
            if (targetSection) {
                targetSection.classList.add('active');
            }

            // Close mobile menu if open
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.add('hidden');

            // Scroll to top
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Mobile menu toggle
        document.getElementById('mobile-menu-btn').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });

        // Hashtag generation functionality
        function generateHashtags() {
            const keyword = document.getElementById('keyword-input').value.trim().toLowerCase();
            
            if (!keyword) {
                alert('Please enter a keyword to generate hashtags.');
                return;
            }

            // Show loading state
            const resultsSection = document.getElementById('results-section');
            const hashtagsGrid = document.getElementById('hashtags-grid');
            
            resultsSection.classList.remove('hidden');
            hashtagsGrid.innerHTML = '<div class="col-span-full text-center py-8"><i class="fas fa-spinner fa-spin text-4xl text-indigo-600 pulse-animation"></i><p class="mt-4 text-lg text-gray-600">Generating hashtags...</p></div>';

            // Simulate API delay for better UX
            setTimeout(() => {
                generatedHashtags = createHashtags(keyword);
                displayHashtags(generatedHashtags);
            }, 1500);
        }

        function createHashtags(keyword) {
            const hashtags = [];
            const baseKeyword = keyword.replace(/\s+/g, '').toLowerCase();
            
            // Base hashtag
            hashtags.push(`#${baseKeyword}`);
            
            // Common prefixes and suffixes
            const prefixes = ['daily', 'best', 'top', 'amazing', 'awesome', 'cool', 'new', 'trending', 'viral', 'popular', 'epic', 'ultimate', 'perfect', 'super', 'mega'];
            const suffixes = ['love', 'life', 'world', 'time', 'day', 'moment', 'vibes', 'goals', 'inspiration', 'motivation', 'journey', 'adventure', 'experience', 'story', 'memories'];
            const general = ['instagood', 'photooftheday', 'beautiful', 'happy', 'fun', 'style', 'amazing', 'followme', 'instadaily', 'bestoftheday', 'smile', 'friends', 'family', 'nature', 'summer'];
            
            // Add prefix combinations
            prefixes.forEach(prefix => {
                hashtags.push(`#${prefix}${baseKeyword}`);
            });
            
            // Add suffix combinations
            suffixes.forEach(suffix => {
                hashtags.push(`#${baseKeyword}${suffix}`);
            });
            
            // Add general hashtags
            general.forEach(tag => {
                hashtags.push(`#${tag}`);
            });

            // Add some creative variations
            if (baseKeyword.length > 4) {
                hashtags.push(`#${baseKeyword.substring(0, 3)}${baseKeyword.slice(-3)}`);
                hashtags.push(`#${baseKeyword}gram`);
                hashtags.push(`#${baseKeyword}addict`);
                hashtags.push(`#${baseKeyword}lover`);
                hashtags.push(`#${baseKeyword}fan`);
            }

            // Shuffle and return first 30 unique hashtags
            const shuffled = hashtags.sort(() => 0.5 - Math.random());
            return [...new Set(shuffled)].slice(0, 30);
        }

        function displayHashtags(hashtags) {
            const hashtagsGrid = document.getElementById('hashtags-grid');
            hashtagsGrid.innerHTML = '';

            hashtags.forEach((hashtag, index) => {
                const hashtagElement = document.createElement('div');
                hashtagElement.className = 'hashtag-item bg-white p-4 rounded-lg card-shadow cursor-pointer border-2 border-transparent hover:border-indigo-300 transition-all duration-300';
                hashtagElement.innerHTML = `
                    <div class="flex items-center justify-between">
                        <span class="text-indigo-600 font-medium">${hashtag}</span>
                        <i class="fas fa-copy text-gray-400 copy-btn"></i>
                    </div>
                `;
                
                hashtagElement.addEventListener('click', () => copyHashtag(hashtag, hashtagElement));
                hashtagsGrid.appendChild(hashtagElement);
            });
        }

        function copyHashtag(hashtag, element) {
            navigator.clipboard.writeText(hashtag).then(() => {
                // Visual feedback
                const copyIcon = element.querySelector('.copy-btn');
                const originalIcon = copyIcon.className;
                copyIcon.className = 'fas fa-check text-green-500';
                element.style.backgroundColor = '#f0fdf4';
                element.style.borderColor = '#22c55e';
                
                setTimeout(() => {
                    copyIcon.className = originalIcon;
                    element.style.backgroundColor = 'white';
                    element.style.borderColor = 'transparent';
                }, 1000);
                
                // Show toast notification
                showToast(`Copied: ${hashtag}`);
            }).catch(err => {
                console.error('Failed to copy: ', err);
                showToast('Failed to copy hashtag', 'error');
            });
        }

        function copyAllHashtags() {
            if (generatedHashtags.length === 0) {
                showToast('No hashtags to copy', 'error');
                return;
            }
            
            const allHashtags = generatedHashtags.join(' ');
            navigator.clipboard.writeText(allHashtags).then(() => {
                showToast('All hashtags copied to clipboard!');
            }).catch(err => {
                console.error('Failed to copy: ', err);
                showToast('Failed to copy hashtags', 'error');
            });
        }

        function showToast(message, type = 'success') {
            const toast = document.createElement('div');
            const bgColor = type === 'success' ? 'bg-green-500' : 'bg-red-500';
            toast.className = `fixed top-4 right-4 ${bgColor} text-white px-6 py-3 rounded-lg shadow-lg z-50 transform translate-x-full transition-transform duration-300`;
            toast.innerHTML = `<i class="fas fa-${type === 'success' ? 'check' : 'exclamation-triangle'} mr-2"></i>${message}`;
            
            document.body.appendChild(toast);
            
            // Animate in
            setTimeout(() => {
                toast.style.transform = 'translateX(0)';
            }, 100);
            
            // Animate out and remove
            setTimeout(() => {
                toast.style.transform = 'translateX(full)';
                setTimeout(() => {
                    document.body.removeChild(toast);
                }, 300);
            }, 3000);
        }

        // Contact form handling
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            showToast('Thank you for your message! We\'ll get back to you soon.');
            this.reset();
        });

        // Enter key support for hashtag generation
        document.getElementById('keyword-input').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                generateHashtags();
            }
        });

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            showSection('home');
        });
    </script>
</body>
</html>
