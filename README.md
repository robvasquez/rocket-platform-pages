# Rocket Platform - Privacy Pages

This directory contains privacy policies and data deletion pages for all apps in the Rocket Platform monorepo.

## 📁 Structure

```
docs/pages/
├── index.html                    # Main landing page
├── crowd-lens/                   # Crowd Lens app pages
│   ├── privacy-policy.html
│   └── delete-account.html
├── donde-esta-el-bus/           # Bus tracking app pages
│   ├── privacy-policy.html
│   └── delete-account.html
├── training-plans-mobile/       # Training plans app pages
│   ├── privacy-policy.html
│   └── delete-account.html
├── mobile-rn/                   # Mobile RN app pages
│   ├── privacy-policy.html
│   └── delete-account.html
├── medical-ai/                  # Medical AI app pages
│   ├── privacy-policy.html
│   └── delete-account.html
└── budget-flow/                 # Budget flow app pages
    ├── privacy-policy.html
    └── delete-account.html
```

## 🚀 Quick Setup for GitHub Pages

### Option 1: Manual Setup

1. **Create GitHub Repository**
   - Go to GitHub.com and create a new **public** repository
   - Name it: `rocket-platform-pages` (or any name you prefer)

2. **Upload Files**
   - Upload all files from this `docs/pages` directory
   - Commit the changes

3. **Enable GitHub Pages**
   - Go to repository **Settings** → **Pages**
   - Select "Deploy from a branch" → **main** branch → **/ (root)**
   - Click **Save**

4. **Get Your URLs**
   After 2-3 minutes, your pages will be live at:
   - **Main page**: `https://[your-username].github.io/rocket-platform-pages/`
   - **Crowd Lens**: `https://[your-username].github.io/rocket-platform-pages/crowd-lens/`
   - **Bus App**: `https://[your-username].github.io/rocket-platform-pages/donde-esta-el-bus/`

### Option 2: Automated Deployment

1. **Update Configuration**
   - Edit `tools/scripts/deploy-github-pages.mjs`
   - Update `repository` and `username` variables

2. **Run Deployment Script**
   ```bash
   cd /Users/robvasquez/projects/rocket-platform
   node tools/scripts/deploy-github-pages.mjs
   ```

## 📱 Google Play Store URLs

Use these URLs in your Google Play Store submissions:

### Crowd Lens
- **Privacy Policy**: `https://[your-username].github.io/rocket-platform-pages/crowd-lens/privacy-policy.html`
- **Data Deletion**: `https://[your-username].github.io/rocket-platform-pages/crowd-lens/delete-account.html`

### ¿Dónde está el bus?
- **Privacy Policy**: `https://[your-username].github.io/rocket-platform-pages/donde-esta-el-bus/privacy-policy.html`
- **Data Deletion**: `https://[your-username].github.io/rocket-platform-pages/donde-esta-el-bus/delete-account.html`

### Other Apps
Replace `[app-name]` with the app slug:
- **Privacy Policy**: `https://[your-username].github.io/rocket-platform-pages/[app-name]/privacy-policy.html`
- **Data Deletion**: `https://[your-username].github.io/rocket-platform-pages/[app-name]/delete-account.html`

## 🔧 Regenerating Pages

To regenerate all privacy pages with updated templates:

```bash
cd /Users/robvasquez/projects/rocket-platform
node tools/scripts/generate-privacy-pages.mjs
```

## ✏️ Customizing Pages

### App-Specific Customization

1. **Edit App Configuration**
   - Modify `tools/scripts/generate-privacy-pages.mjs`
   - Update the `apps` array with app-specific details

2. **Manual Customization**
   - Edit individual HTML files in each app directory
   - Add app-specific features, data types, or contact information

### Template Customization

- **Privacy Policy Template**: Edit the `privacyPolicyTemplate` function
- **Delete Account Template**: Edit the `deleteAccountTemplate` function
- **Styling**: Modify CSS in the `<style>` sections

## 📋 Apps Included

| App | Status | Description | Email |
|-----|--------|-------------|-------|
| Crowd Lens | Active | Photo sharing for events | privacy@crowdlens.app |
| ¿Dónde está el bus? | Active | Real-time bus tracking | privacy@dondeestaelbus.app |
| Training Plans Mobile | Development | Fitness training plans | privacy@trainingplans.app |
| Mobile RN | Development | React Native app | privacy@mobilern.app |
| Medical AI | Development | AI medical assistance | privacy@medicalai.app |
| Budget Flow | Active | Personal finance management | privacy@budgetflow.app |

## 🔄 Adding New Apps

1. **Add to Configuration**
   - Edit `tools/scripts/generate-privacy-pages.mjs`
   - Add new app to the `apps` array

2. **Regenerate Pages**
   ```bash
   node tools/scripts/generate-privacy-pages.mjs
   ```

3. **Deploy Updates**
   ```bash
   node tools/scripts/deploy-github-pages.mjs
   ```

## 🛠️ Nx Integration

### Available Commands

```bash
# Generate all privacy pages
nx run-many --target=generate-privacy-pages --all

# Deploy to GitHub Pages
nx run-many --target=deploy-github-pages --all

# Build specific app pages
nx generate-privacy-pages crowd-lens
```

### Project Configuration

Add to your `nx.json`:

```json
{
  "targetDefaults": {
    "generate-privacy-pages": {
      "executor": "nx:run-commands",
      "options": {
        "command": "node tools/scripts/generate-privacy-pages.mjs"
      }
    },
    "deploy-github-pages": {
      "executor": "nx:run-commands",
      "options": {
        "command": "node tools/scripts/deploy-github-pages.mjs"
      }
    }
  }
}
```

## 📞 Support

For questions or issues:
- **Email**: privacy@rocketplatform.com
- **Developer**: Rob Vasquez
- **Platform**: Rocket Platform

---

**Note**: These pages are designed for Google Play Store compliance and include all necessary privacy policy elements and data deletion procedures for all apps in the Rocket Platform monorepo.
