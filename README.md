
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Applied Data Science Repository Generator</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .card {
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.95);
        }
        
        .code-block {
            font-family: 'Courier New', monospace;
            background: #1e293b;
            color: #e2e8f0;
        }
        
        .directory-tree li::before {
            content: "📁 ";
        }
        
        .file-tree li::before {
            content: "📄 ";
        }
        
        .step-card {
            transition: all 0.3s ease;
        }
        
        .step-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }
        
        .repo-item {
            transition: all 0.2s ease;
        }
        
        .repo-item:hover {
            background: rgba(59, 130, 246, 0.1);
            border-left: 4px solid #3b82f6;
        }
        
        .loading {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="min-h-screen p-4 md:p-8">
    <div class="max-w-7xl mx-auto">
        <!-- Header -->
        <header class="text-center mb-10 fade-in">
            <h1 class="text-4xl md:text-5xl font-bold text-white mb-4">
                <i class="fas fa-rocket mr-3"></i>
                Applied Data Science Repository Generator
            </h1>
            <p class="text-xl text-white/90 mb-6">
                One-click setup for professional data science projects
            </p>
            <div class="flex flex-wrap justify-center gap-4 mb-8">
                <span class="px-4 py-2 bg-white/20 text-white rounded-full">
                    <i class="fas fa-code mr-2"></i>Python
                </span>
                <span class="px-4 py-2 bg-white/20 text-white rounded-full">
                    <i class="fas fa-project-diagram mr-2"></i>MLOps
                </span>
                <span class="px-4 py-2 bg-white/20 text-white rounded-full">
                    <i class="fas fa-chart-line mr-2"></i>Best Practices
                </span>
                <span class="px-4 py-2 bg-white/20 text-white rounded-full">
                    <i class="fab fa-docker mr-2"></i>Docker
                </span>
            </div>
        </header>

        <!-- Main Container -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-10">
            <!-- Left Panel: Configuration -->
            <div class="lg:col-span-2">
                <div class="card rounded-2xl shadow-2xl p-6 mb-8">
                    <h2 class="text-2xl font-bold text-gray-800 mb-6">
                        <i class="fas fa-cogs mr-2 text-blue-500"></i>
                        Repository Configuration
                    </h2>
                    
                    <!-- Configuration Form -->
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <div>
                            <label class="block text-gray-700 mb-2">
                                <i class="fas fa-folder mr-2"></i>Repository Name
                            </label>
                            <input type="text" id="repoName" 
                                   class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                                   placeholder="applied-data-science" 
                                   value="applied-data-science">
                        </div>
                        
                        <div>
                            <label class="block text-gray-700 mb-2">
                                <i class="fas fa-user mr-2"></i>Your Name
                            </label>
                            <input type="text" id="userName" 
                                   class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                                   placeholder="Data Scientist"
                                   value="Your Name">
                        </div>
                        
                        <div>
                            <label class="block text-gray-700 mb-2">
                                <i class="fas fa-envelope mr-2"></i>Email
                            </label>
                            <input type="email" id="userEmail" 
                                   class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                                   placeholder="you@example.com"
                                   value="you@example.com">
                        </div>
                        
                        <div>
                            <label class="block text-gray-700 mb-2">
                                <i class="fas fa-balance-scale mr-2"></i>License
                            </label>
                            <select id="licenseType" 
                                    class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <option value="MIT">MIT License</option>
                                <option value="Apache">Apache 2.0</option>
                                <option value="GPL">GPL v3</option>
                                <option value="BSD">BSD 3-Clause</option>
                            </select>
                        </div>
                    </div>
                    
                    <!-- Project Selection -->
                    <div class="mb-8">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">
                            <i class="fas fa-tasks mr-2 text-green-500"></i>
                            Include Sample Projects
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <label class="flex items-center p-4 border border-gray-200 rounded-lg hover:bg-blue-50 cursor-pointer">
                                <input type="checkbox" class="mr-3 h-5 w-5 text-blue-600" checked>
                                <div>
                                    <span class="font-medium">Customer Churn Prediction</span>
                                    <p class="text-sm text-gray-600">Predict customer churn using ML</p>
                                </div>
                            </label>
                            <label class="flex items-center p-4 border border-gray-200 rounded-lg hover:bg-blue-50 cursor-pointer">
                                <input type="checkbox" class="mr-3 h-5 w-5 text-blue-600" checked>
                                <div>
                                    <span class="font-medium">Sales Forecasting</span>
                                    <p class="text-sm text-gray-600">Time series forecasting models</p>
                                </div>
                            </label>
                            <label class="flex items-center p-4 border border-gray-200 rounded-lg hover:bg-blue-50 cursor-pointer">
                                <input type="checkbox" class="mr-3 h-5 w-5 text-blue-600" checked>
                                <div>
                                    <span class="font-medium">Image Classification</span>
                                    <p class="text-sm text-gray-600">CNN for image recognition</p>
                                </div>
                            </label>
                            <label class="flex items-center p-4 border border-gray-200 rounded-lg hover:bg-blue-50 cursor-pointer">
                                <input type="checkbox" class="mr-3 h-5 w-5 text-blue-600" checked>
                                <div>
                                    <span class="font-medium">NLP Sentiment Analysis</span>
                                    <p class="text-sm text-gray-600">BERT for text classification</p>
                                </div>
                            </label>
                        </div>
                    </div>
                    
                    <!-- Advanced Options -->
                    <div class="mb-8">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">
                            <i class="fas fa-sliders-h mr-2 text-purple-500"></i>
                            Advanced Options
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600" checked>
                                <span>Docker Support</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600" checked>
                                <span>CI/CD (GitHub Actions)</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600" checked>
                                <span>MLflow Tracking</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600" checked>
                                <span>FastAPI Deployment</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600" checked>
                                <span>Streamlit Dashboard</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 h-5 w-5 text-blue-600">
                                <span>Kubernetes Deployment</span>
                            </label>
                        </div>
                    </div>
                    
                    <!-- Generate Button -->
                    <button onclick="generateRepository()" 
                            class="w-full py-4 bg-gradient-to-r from-blue-600 to-purple-600 text-white font-bold rounded-lg hover:from-blue-700 hover:to-purple-700 transition-all duration-300 transform hover:-translate-y-1">
                        <i class="fas fa-magic mr-2"></i>
                        Generate Repository
                    </button>
                </div>
                
                <!-- Preview -->
                <div class="card rounded-2xl shadow-2xl p-6">
                    <h2 class="text-2xl font-bold text-gray-800 mb-6">
                        <i class="fas fa-eye mr-2 text-yellow-500"></i>
                        Repository Preview
                    </h2>
                    <div id="previewContent" class="code-block rounded-lg p-4 overflow-x-auto">
                        <pre id="previewCode" class="text-sm">
<!-- Preview will be generated here -->
                        </pre>
                    </div>
                </div>
            </div>
            
            <!-- Right Panel: Features & Structure -->
            <div class="space-y-8">
                <!-- Features -->
                <div class="card rounded-2xl shadow-2xl p-6">
                    <h2 class="text-2xl font-bold text-gray-800 mb-6">
                        <i class="fas fa-star mr-2 text-yellow-500"></i>
                        Features
                    </h2>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Professional project structure</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Complete MLOps pipeline</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Best practices & documentation</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Docker & deployment ready</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Sample projects included</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fas fa-check-circle text-green-500 mr-3 mt-1"></i>
                            <span>Testing & CI/CD setup</span>
                        </li>
                    </ul>
                </div>
                
                <!-- Structure Tree -->
                <div class="card rounded-2xl shadow-2xl p-6">
                    <h2 class="text-2xl font-bold text-gray-800 mb-6">
                        <i class="fas fa-sitemap mr-2 text-indigo-500"></i>
                        Directory Structure
                    </h2>
                    <div class="space-y-2 text-sm">
                        <div class="directory-tree font-mono">
                            <ul class="list-none pl-4 space-y-1">
                                <li class="repo-item p-2 rounded">
                                    <span class="font-bold">applied-data-science/</span>
                                    <ul class="list-none pl-6 space-y-1 mt-1">
                                        <li class="file-tree p-1">📄 README.md</li>
                                        <li class="file-tree p-1">📄 requirements.txt</li>
                                        <li class="file-tree p-1">📄 setup.py</li>
                                        <li>📁 projects/
                                            <ul class="list-none pl-6">
                                                <li>📁 01-customer-churn/</li>
                                                <li>📁 02-sales-forecasting/</li>
                                                <li>📁 03-image-classification/</li>
                                                <li>📁 04-nlp-sentiment/</li>
                                            </ul>
                                        </li>
                                        <li>📁 notebooks/
                                            <ul class="list-none pl-6">
                                                <li>📁 exploratory/</li>
                                                <li>📁 modeling/</li>
                                                <li>📁 visualization/</li>
                                            </ul>
                                        </li>
                                        <li>📁 src/
                                            <ul class="list-none pl-6">
                                                <li>📁 data/</li>
                                                <li>📁 features/</li>
                                                <li>📁 models/</li>
                                                <li>📁 visualization/</li>
                                            </ul>
                                        </li>
                                        <li>📁 data/
                                            <ul class="list-none pl-6">
                                                <li>📁 raw/</li>
                                                <li>📁 processed/</li>
                                                <li>📁 external/</li>
                                            </ul>
                                        </li>
                                    </ul>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                
                <!-- Quick Actions -->
                <div class="card rounded-2xl shadow-2xl p-6">
                    <h2 class="text-2xl font-bold text-gray-800 mb-6">
                        <i class="fas fa-bolt mr-2 text-red-500"></i>
                        Quick Actions
                    </h2>
                    <div class="grid grid-cols-2 gap-4">
                        <button onclick="copyToClipboard()" 
                                class="p-3 bg-blue-100 text-blue-700 rounded-lg hover:bg-blue-200 transition-colors">
                            <i class="fas fa-copy mr-2"></i>Copy Structure
                        </button>
                        <button onclick="downloadAsZip()" 
                                class="p-3 bg-green-100 text-green-700 rounded-lg hover:bg-green-200 transition-colors">
                            <i class="fas fa-download mr-2"></i>Download ZIP
                        </button>
                        <button onclick="openInGitHub()" 
                                class="p-3 bg-purple-100 text-purple-700 rounded-lg hover:bg-purple-200 transition-colors">
                            <i class="fab fa-github mr-2"></i>GitHub Template
                        </button>
                        <button onclick="deployToCloud()" 
                                class="p-3 bg-orange-100 text-orange-700 rounded-lg hover:bg-orange-200 transition-colors">
                            <i class="fas fa-cloud mr-2"></i>Deploy Cloud
                        </button>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Steps -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-10">
            <div class="step-card card rounded-2xl shadow-xl p-6 text-center">
                <div class="text-4xl text-blue-500 mb-4">1</div>
                <h3 class="text-xl font-bold mb-2">Configure</h3>
                <p class="text-gray-600">Set up your repository name and options</p>
            </div>
            <div class="step-card card rounded-2xl shadow-xl p-6 text-center">
                <div class="text-4xl text-green-500 mb-4">2</div>
                <h3 class="text-xl font-bold mb-2">Generate</h3>
                <p class="text-gray-600">Create the complete structure</p>
            </div>
            <div class="step-card card rounded-2xl shadow-xl p-6 text-center">
                <div class="text-4xl text-purple-500 mb-4">3</div>
                <h3 class="text-xl font-bold mb-2">Customize</h3>
                <p class="text-gray-600">Add your data and models</p>
            </div>
            <div class="step-card card rounded-2xl shadow-xl p-6 text-center">
                <div class="text-4xl text-red-500 mb-4">4</div>
                <h3 class="text-xl font-bold mb-2">Deploy</h3>
                <p class="text-gray-600">Run and deploy your projects</p>
            </div>
        </div>
        
        <!-- Footer -->
        <footer class="text-center text-white/80">
            <p>Applied Data Science Repository Generator • Built with ❤️ for the ML community</p>
            <p class="mt-2 text-sm">© 2024 • All templates are MIT Licensed</p>
        </footer>
    </div>
    
    <!-- Progress Modal -->
    <div id="progressModal" class="fixed inset-0 bg-black/50 hidden items-center justify-center z-50 p-4">
        <div class="bg-white rounded-2xl p-8 max-w-md w-full">
            <div class="text-center">
                <div class="text-6xl mb-6">
                    <i class="fas fa-cogs loading text-blue-500"></i>
                </div>
                <h3 class="text-2xl font-bold mb-4">Generating Repository</h3>
                <p class="text-gray-600 mb-6">Creating your applied data science structure...</p>
                <div class="w-full bg-gray-200 rounded-full h-2 mb-6">
                    <div id="progressBar" class="bg-green-600 h-2 rounded-full w-0 transition-all duration-500"></div>
                </div>
                <div id="progressText" class="text-sm text-gray-500 mb-4">Initializing...</div>
                <button onclick="hideProgress()" 
                        class="px-6 py-2 bg-gray-200 text-gray-700 rounded-lg hover:bg-gray-300">
                    Cancel
                </button>
            </div>
        </div>
    </div>
    
    <!-- Success Modal -->
    <div id="successModal" class="fixed inset-0 bg-black/50 hidden items-center justify-center z-50 p-4">
        <div class="bg-white rounded-2xl p-8 max-w-md w-full">
            <div class="text-center">
                <div class="text-6xl mb-6 text-green-500">
                    <i class="fas fa-check-circle"></i>
                </div>
                <h3 class="text-2xl font-bold mb-4">Repository Created!</h3>
                <p class="text-gray-600 mb-6">Your applied data science repository is ready.</p>
                <div class="space-y-3">
                    <button onclick="downloadZip()" 
                            class="w-full py-3 bg-green-600 text-white rounded-lg hover:bg-green-700">
                        <i class="fas fa-download mr-2"></i>Download as ZIP
                    </button>
                    <button onclick="copyCommands()" 
                            class="w-full py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
                        <i class="fas fa-terminal mr-2"></i>Copy Setup Commands
                    </button>
                    <button onclick="closeSuccess()" 
                            class="w-full py-3 bg-gray-200 text-gray-700 rounded-lg hover:bg-gray-300">
                        Close
                    </button>
                </div>
            </div>
        </div>
    </div>
    
    <script src="script.js"></script>
</body>
</html>
#!/usr/bin/env python3
"""
Applied Data Science Repository Generator - Backend API
"""

import os
import json
import zipfile
import tempfile
import shutil
from pathlib import Path
from datetime import datetime
from flask import Flask, request, jsonify, send_file, render_template
from flask_cors import CORS
import yaml

app = Flask(__name__)
CORS(app)

# Template structures
TEMPLATES = {
    "readme": """# {repo_name}

A professional applied data science repository with best practices.

## 🚀 Features

- Complete project structure
- MLOps pipeline
- Docker support
- Sample projects
- Testing framework

## 📁 Structure
