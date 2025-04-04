# Deployment Instructions for Grace Huckins' Website

This document provides step-by-step instructions for deploying your new website and connecting it to your domain (gracehuckins.com).

## Option 1: GitHub Pages (Recommended)

GitHub Pages is a free hosting service that allows you to deploy static websites directly from a GitHub repository.

### Prerequisites
- A GitHub account (free)
- Git installed on your computer
- Basic familiarity with command line operations

### Step 1: Create a GitHub Repository
1. Go to [GitHub](https://github.com) and sign in to your account
2. Click the "+" icon in the top right corner and select "New repository"
3. Name your repository `gracehuckins.github.io` (this specific name is important)
4. Make the repository public
5. Click "Create repository"

### Step 2: Upload Your Website Files
```bash
# Clone the repository to your local machine
git clone https://github.com/yourusername/gracehuckins.github.io.git

# Copy all website files into the repository folder
cp -r /path/to/website_project/* /path/to/gracehuckins.github.io/

# Navigate to the repository folder
cd gracehuckins.github.io

# Add all files to git
git add .

# Commit the changes
git commit -m "Initial website commit"

# Push to GitHub
git push origin main
```

### Step 3: Configure GitHub Pages
1. Go to your repository on GitHub
2. Click on "Settings"
3. Scroll down to the "GitHub Pages" section
4. Under "Source", select "main" branch
5. Click "Save"
6. Your site will be published at `https://yourusername.github.io`

### Step 4: Connect Your Custom Domain
1. Go to your domain registrar's website (where you purchased gracehuckins.com)
2. Find the DNS settings for your domain
3. Add the following DNS records:
   - Type: A, Host: @, Value: 185.199.108.153
   - Type: A, Host: @, Value: 185.199.109.153
   - Type: A, Host: @, Value: 185.199.110.153
   - Type: A, Host: @, Value: 185.199.111.153
   - Type: CNAME, Host: www, Value: yourusername.github.io

4. In your GitHub repository:
   - Go to "Settings" > "GitHub Pages"
   - Under "Custom domain", enter `gracehuckins.com`
   - Check "Enforce HTTPS" (recommended for security)
   - Click "Save"

5. Create a file named `CNAME` in the root of your repository with the following content:
```
gracehuckins.com
```

### Step 5: Verify Deployment
1. Wait for DNS changes to propagate (can take up to 24-48 hours)
2. Visit `https://gracehuckins.com` to verify your site is live

## Option 2: Netlify (Alternative)

Netlify is another excellent free hosting service for static websites with an easy-to-use interface.

### Prerequisites
- A Netlify account (free)

### Step 1: Create a Netlify Account
1. Go to [Netlify](https://www.netlify.com/) and sign up for a free account

### Step 2: Deploy Your Site
1. Log in to your Netlify account
2. Click "New site from Git" if you're using Git, or simply drag and drop your website folder onto the Netlify dashboard
3. If using the drag and drop method:
   - Compress your website folder into a ZIP file
   - Drag and drop the ZIP file onto the Netlify dashboard
   - Netlify will automatically deploy your site

### Step 3: Configure Your Domain
1. From your Netlify dashboard, select your site
2. Go to "Site settings" > "Domain management" > "Custom domains"
3. Click "Add custom domain"
4. Enter `gracehuckins.com` and click "Verify"
5. Choose "Yes, add domain"
6. Follow Netlify's instructions to update your DNS settings at your domain registrar
   - You'll either need to update nameservers or add specific DNS records
7. Enable HTTPS by clicking "Verify DNS configuration" and then "Let's Encrypt certificate"

### Step 4: Verify Deployment
1. Wait for DNS changes to propagate (can take up to 24-48 hours)
2. Visit `https://gracehuckins.com` to verify your site is live

## Maintenance and Updates

To update your website in the future:

### For GitHub Pages:
1. Make changes to your local repository
2. Commit and push the changes to GitHub
```bash
git add .
git commit -m "Update website content"
git push origin main
```
3. GitHub will automatically rebuild and deploy your site

### For Netlify:
1. Make changes to your website files
2. Upload the updated files using the Netlify dashboard or Git integration
3. Netlify will automatically rebuild and deploy your site

## Troubleshooting

### Domain Connection Issues
- DNS changes can take 24-48 hours to fully propagate
- Verify your DNS records are correctly set up at your domain registrar
- Check for typos in domain names or DNS records

### Website Not Updating
- Clear your browser cache (Ctrl+F5 or Cmd+Shift+R)
- Check deployment logs in GitHub or Netlify for any errors
- Verify that all files were correctly uploaded

### HTTPS Issues
- Ensure "Enforce HTTPS" is enabled in your hosting settings
- Wait for SSL certificate to be issued (can take a few hours)

If you encounter any issues during deployment, feel free to reach out for assistance.
