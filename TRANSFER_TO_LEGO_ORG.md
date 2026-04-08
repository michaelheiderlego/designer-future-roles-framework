# Transfer to LEGO Organization

## Current Status ✅

Your framework is **live and working**:
- **Repository**: https://github.com/michaelheiderlego/designer-future-roles-framework
- **Live Site**: https://michaelheiderlego.github.io/designer-future-roles-framework/
- **Status**: Building (will be live in ~1 minute)

All features are working:
- ✅ Circular and List views
- ✅ Rich content for AI-Augmented zone (links, screenshots)
- ✅ Updated title: "The Future of Design Skills"
- ✅ Export/Import functionality
- ✅ Auto-save to browser localStorage

---

## To Transfer to LEGO Organization

The LEGO organization has restrictions that prevent members from creating public repositories directly. Here's how to proceed:

### Option 1: Request Admin Assistance (Recommended)

Contact a LEGO GitHub organization admin and ask them to:

1. **Transfer the repository**:
   - Go to: https://github.com/michaelheiderlego/designer-future-roles-framework/settings
   - Scroll to "Danger Zone" → "Transfer ownership"
   - Transfer to organization: **LEGO**
   - New repository name: **future-of-design-skills**

2. **Enable GitHub Pages**:
   ```bash
   gh api repos/LEGO/future-of-design-skills/pages -X POST \
     -F 'source[branch]=main' -F 'source[path]=/'
   ```

   Or manually:
   - Go to Settings → Pages
   - Source: `main` branch, `/` (root)
   - Save

### Option 2: Request Permission Change

Ask the LEGO GitHub admin to:
1. Grant you repository creation permissions in the LEGO organization
2. Update organization settings to allow members to create public repositories
3. Then you can transfer the repo yourself

### Option 3: Keep on Personal Account (Temporary)

For now, your colleagues can use:
- **https://michaelheiderlego.github.io/designer-future-roles-framework/**

Then transfer to LEGO org when ready. GitHub Pages will automatically redirect to the new URL after transfer.

---

## After Transfer

The new URLs will be:
- **Repository**: https://github.com/LEGO/future-of-design-skills
- **Live Site**: https://lego.github.io/future-of-design-skills/

Share with your team and start collaborating!

---

## How Colleagues Can Contribute

### During Workshops:
1. Open the live site on a shared screen
2. Add items collaboratively
3. **Export** the framework at the end
4. Share the JSON file via email/Slack

### Async Collaboration:
1. Each person opens the site and adds their ideas
2. Everyone **exports** their version (JSON file)
3. Someone imports all versions and merges the best ideas
4. Share the merged version

### Key Features for Collaboration:
- **Import/Export** - Share frameworks as JSON files
- **Local Storage** - Each person's edits are saved in their browser
- **No login required** - Just share the URL

---

## Who to Contact

Look for LEGO GitHub organization admins in:
- Your IT/DevOps team
- GitHub organization owners
- Digital Technology leadership

You can check who has admin access with:
```bash
gh api orgs/LEGO/members?role=admin --jq '.[].login'
```

---

## Questions?

If you need any changes to the framework before going live, let me know!
