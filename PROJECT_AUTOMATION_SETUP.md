# Project Automation Rules Setup Guide

After migrating issues from the private repository, you'll need to manually set up automation rules for the project boards. GitHub's API doesn't support creating these rules programmatically, so follow these steps:

## Prerequisites
- Projects have been created: "UX Improvements" and "Architecture Improvements"
- Issues have been migrated from the private repository

## Setting Up Automation Rules

### 1. Access Project Settings
1. Go to https://github.com/endian-dev
2. Click on the "Projects" tab
3. Select the project you want to configure
4. Click on the ⚙️ (Settings) icon in the top right

### 2. Configure Workflows

#### For Both Projects (UX Improvements & Architecture Improvements)

**Auto-add issues with labels:**
1. Click "Workflows" in the left sidebar
2. Click "Add workflow" → "Item added to project"
3. Configure:
   - **When**: An issue or pull request is added to the project
   - **Do**: Set status to "Todo" (or your preferred default column)

**Auto-archive closed items:**
1. Click "Add workflow" → "Item closed"
2. Configure:
   - **When**: An issue or pull request is closed
   - **Do**: Archive item

**Auto-move items based on labels:**
1. Click "Add workflow" → "Item edited"
2. Configure multiple rules:
   
   For "In Progress" status:
   - **When**: Label "in-progress" is added
   - **Do**: Set status to "In Progress"
   
   For "Blocked" status:
   - **When**: Label "blocked" is added  
   - **Do**: Set status to "Blocked"
   
   For "Ready for Test" status:
   - **When**: Label "ready-for-test" is added
   - **Do**: Set status to "Ready for Test"

### 3. Set Up Auto-add Rules

To automatically add issues to projects based on labels:

**For UX Improvements Project:**
1. In Workflows, click "Add workflow" → "Auto-add to project"
2. Configure:
   - **Filter**: `is:issue label:ui-ux`
   - This will auto-add any issue with the "ui-ux" label

**For Architecture Improvements Project:**
1. In Workflows, click "Add workflow" → "Auto-add to project"
2. Configure:
   - **Filter**: `is:issue label:performance,enhancement,security`
   - This will auto-add issues with performance, enhancement, or security labels

### 4. Configure Project Fields

If you want to track additional information:

1. Click "Settings" → "Custom fields"
2. Add fields like:
   - **Priority**: Single select (P0-critical, P1-high, P2-medium, P3-low)
   - **Estimate**: Number field for story points
   - **Sprint**: Iteration field for sprint planning

### 5. Set Up Views

Create different views for better organization:

1. Click "New view" button
2. Examples:
   - **"High Priority"**: Filter by priority = P0-critical OR P1-high
   - **"Current Sprint"**: Filter by sprint = current iteration
   - **"Blocked Items"**: Filter by status = Blocked
   - **"By Platform"**: Group by platform labels

## Recommended Workflow States

For consistency across projects, use these status columns:

1. **📋 Todo** - New items, not yet started
2. **🚧 In Progress** - Actively being worked on
3. **⏸️ Blocked** - Waiting on external factors
4. **👀 In Review** - Ready for review/testing
5. **✅ Done** - Completed items

## Linking Issues to Projects

After migration, you'll need to add existing issues to projects:

### Bulk Add via GitHub UI:
1. Go to the project
2. Click "+ Add items"
3. Search for issues using filters like:
   - `is:issue is:open label:ui-ux` (for UX project)
   - `is:issue is:open label:performance` (for Architecture project)
4. Select all relevant issues
5. Click "Add selected items"

### Via Command Line:
```bash
# Add specific issue to project
gh project item-add PROJECT_NUMBER --owner endian-dev --url https://github.com/endian-dev/Shokken-Issues/issues/ISSUE_NUMBER
```

## Maintenance Tips

1. **Regular Reviews**: Weekly review of project boards to ensure items are in correct columns
2. **Label Hygiene**: Ensure issues have appropriate labels for automation to work
3. **Archive Completed**: Regularly archive done items to keep boards clean
4. **Update Automation**: Adjust rules as your workflow evolves

## Troubleshooting

**Issues not auto-adding to projects:**
- Check that the issue has the correct label
- Verify the auto-add filter syntax
- Ensure the workflow is enabled

**Status not updating automatically:**
- Confirm the label matches exactly (case-sensitive)
- Check that the workflow trigger is set correctly
- Verify the target column exists

**Items stuck in wrong column:**
- Manually drag to correct column
- Check for conflicting labels
- Review workflow priority order