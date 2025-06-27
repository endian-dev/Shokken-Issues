# Issue Reporting Guidelines

This guide provides detailed instructions for creating effective issue reports that help us address problems quickly.

## 📋 Before You Submit

### 1. Search Existing Issues
- Use the search bar with relevant keywords
- Check both open and closed issues
- Look for similar problems even if worded differently
- Check our [Known Issues](KNOWN_ISSUES.md)

### 2. Gather Information
Before creating an issue, collect:
- App version number
- Platform and OS version
- Steps to reproduce
- Error messages or logs
- Screenshots or screen recordings

## 🐛 Writing a Good Bug Report

### Title
- Be specific and descriptive
- Include the affected feature/component
- Avoid generic titles

✅ Good: "Login button unresponsive on Android after timeout"
❌ Bad: "App doesn't work"

### Description Structure

#### 1. Summary
Brief overview of the issue in 1-2 sentences.

#### 2. Environment
```
- App Version: 1.2.3
- Platform: Android
- OS Version: Android 13
- Device: Samsung Galaxy S22
- Network: WiFi/Cellular
```

#### 3. Steps to Reproduce
1. Open the app
2. Navigate to Settings
3. Click on "Account"
4. Observe the error

#### 4. Expected Behavior
What should happen when following these steps.

#### 5. Actual Behavior
What actually happens, including any error messages.

#### 6. Additional Context
- How often does this occur? (Always/Sometimes/Rarely)
- When did it start happening?
- Any workarounds discovered?

### Supporting Materials
- **Screenshots**: Use annotations to highlight issues
- **Logs**: Include relevant portions, not entire files
- **Videos**: For complex interactions or intermittent issues

## ✨ Writing a Good Feature Request

### Title
Clearly state what you want to add or improve.

✅ Good: "Add dark mode theme option"
❌ Bad: "Make app better"

### Structure

#### 1. Problem Statement
Explain the problem or limitation you're facing.

#### 2. Proposed Solution
Describe your ideal solution in detail.

#### 3. Alternatives Considered
What other approaches have you thought about?

#### 4. Use Cases
Provide real-world scenarios where this would help.

#### 5. Mockups (Optional)
Visual representations can be very helpful.

## 📚 Documentation Issues

### Be Specific
- Quote the exact text that's incorrect
- Provide the correct information if known
- Include the documentation URL or section

### Types of Documentation Issues
- Factual errors
- Outdated information
- Missing information
- Unclear explanations
- Broken links
- Grammar/spelling

## ❓ Asking Good Questions

### Before Asking
1. Check the [FAQ](../README.md#-frequently-asked-questions)
2. Read the documentation
3. Search previous questions
4. Try troubleshooting steps

### Question Format
- **Context**: What are you trying to achieve?
- **What you've tried**: List your attempts
- **Specific question**: Be clear and focused
- **Environment**: Include relevant details

## 🚫 What NOT to Include

### Never Share:
- Passwords or authentication tokens
- API keys or secrets
- Personal information (email, phone, address)
- Private server URLs
- Proprietary code or data
- Credit card information

### Sanitize Your Data
Replace sensitive information with placeholders:
- `user@example.com` instead of real emails
- `XXX-XXX-XXXX` for phone numbers
- `[REDACTED]` for sensitive values

## 🏷️ Label Etiquette

Don't add labels yourself - our team will label issues appropriately. However, understanding our label system helps you provide relevant information:

- **Type**: Determined by issue template
- **Priority**: Based on impact and severity
- **Platform**: Mention all affected platforms
- **Status**: Managed by our team

## 📝 Issue Templates

Always use the provided templates:
1. They ensure you include necessary information
2. They help us process issues faster
3. They maintain consistency

If your issue doesn't fit a template, choose the closest one and explain in the description.

## 🔄 Following Up

### Do:
- Respond to questions promptly
- Provide additional information when requested
- Update if you find a solution or workaround
- Be patient - we review all issues

### Don't:
- Bump issues with "+1" or "me too" (use reactions instead)
- Create duplicate issues if you don't get immediate response
- Demand immediate fixes
- Be disrespectful to maintainers or community

## 🎯 Examples

### Good Bug Report Example
```markdown
Title: Profile image upload fails with "Network Error" on iOS 16.5

Description:
When attempting to upload a profile image on iOS, the app consistently shows a "Network Error" message, even with stable internet connection.

Environment:
- App Version: 2.1.0
- Platform: iOS
- OS Version: 16.5
- Device: iPhone 14 Pro
- Network: WiFi (tested on multiple networks)

Steps to Reproduce:
1. Open the app and log in
2. Go to Profile > Edit Profile
3. Tap "Change Photo"
4. Select any image from photo library
5. Tap "Save"

Expected: Image uploads and profile updates
Actual: "Network Error" message appears after 5-10 seconds

Additional Context:
- Started after updating to iOS 16.5
- Other network features work fine
- Tried with images of various sizes
- Console shows: "Error: timeout exceeded"
```

### Good Feature Request Example
```markdown
Title: Add biometric authentication for app login

Problem:
Currently, users must enter their password every time they open the app, which is inconvenient and may discourage use of strong passwords.

Proposed Solution:
Implement Face ID/Touch ID authentication as an optional login method:
- Initial setup in Settings > Security
- Fallback to password if biometric fails
- Re-authenticate after 30 days for security

Alternatives Considered:
- PIN code: Less secure than biometrics
- Remember me: Security concern on shared devices
- OAuth: Requires internet connection

Use Cases:
1. Quick access for frequent users
2. Improved security (encourages strong passwords)
3. Better accessibility for users with typing difficulties
```

## 💡 Pro Tips

1. **One issue per report** - Don't combine multiple problems
2. **Use markdown** - Format code, lists, and sections
3. **Be objective** - Stick to facts, avoid emotional language
4. **Test first** - Ensure the issue is reproducible
5. **Update your issue** - If you find new information

Remember: The better your issue report, the faster we can help!