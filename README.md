# Telme Public API Documentation

Welcome to the official documentation for **Telme Public APIs**. This repository serves as a central place for developers and partners to explore the available API endpoints, understand how to authenticate, and learn how to integrate with Telme’s digital ecosystem.

## 📦 About Telme
**Telme** is a comprehensive platform for managing field service operations, mobile workforce, logistics, and customer interactions. Our system helps companies streamline daily operations by digitizing job planning, documentation, reporting, and communication.

## 📘 What You'll Find in This Repository
This GitHub repository contains:

- Full API specifications in Markdown
- Example requests/responses in JSON
- Schema definitions (where applicable)
- API changelog
- PDF versions for download

## 🚀 Getting Started with the API
All Telme public APIs are RESTful and return data in JSON format.

### Base URL
```
https://api.telme.se/v1/
```

### Authentication
Most APIs require an active session token obtained from a successful login request. Refer to the `Authentication.md` file for details.

### Example Request
```
GET /job?session=abc123&job_no=1001
```

### Example Response
```json
{
  "job": {
    "job_no": 1001,
    "title": "Maintenance Visit",
    "status": "OPEN",
    ...
  }
}
```

## 📫 Support & Contact
If you have any questions, want to report bugs, or request new API features:

- 📧 Email: [support@telme.se](mailto:support@telme.se)
- 🌐 Website: [www.telme.se](https://www.telme.se)
- 📄 License: See `LICENSE.md` for terms of use

## 🤝 Contributing
If you are a partner or 3rd party developer looking to contribute to or extend Telme’s APIs, please contact our developer relations team for onboarding.

## 📌 Notes
- All API calls must be made over HTTPS.
- Please respect rate limiting policies.
- Never share your session tokens publicly.

---

Made with ❤️ by the Telme Engineering Team

# Telme
Telme public documentation 
