# Overview

## Customer Relationship Interaction Manager (CRI) App

Welcome to the **Customer Relationship Interaction Manager (CRI) App**—a powerful, intuitive tool designed to revolutionize the way businesses manage and optimize customer interactions. This document provides an overview of the app, its features, installation, and usage instructions.

## 📝 About the Project

The CRI app is designed to help businesses streamline and improve their customer interactions. Unlike traditional CRM systems, this app focuses on real-time communication, actionable insights, and tailored solutions to enhance customer relationships.

Our mission is to empower businesses with the tools they need to connect with customers more effectively and foster long-term loyalty.

---

## 🌟 Features

- **Streamlined Customer Interactions**: Manage customer touchpoints effortlessly in one platform (Missions,feedbacks,decisions).
- **Real-Time Communication**: Instant notifications and interaction tracking for faster responses.
- **Actionable Insights**: Leverage data-driven recommendations to improve customer engagement (Statistics).
- **Customizable Workflows**: Adaptable for businesses of any size and industry.
- **User-Friendly Interface**: Designed for simplicity and ease of use.

---

## 💻 Technologies Used in this app

- **Backend**: [Node.js]
- **Database**: [MySql]
- **Mobile_Database**: [Hive,SharedPreferences]
- **State Management**: [Bloc(cubit)]
- **Other Tools**: [socket.io]

---

### Installation

1. Clone the repository:

   Github CLi:
   gh repo clone mformatik/Mformatik_CRM_Manager

2. run flutter pub get :
   flutter CLi:

   (**Github CLi**:).
   gh repo clone mformatik/Mformatik_CRM_Manager

3. run flutter pub get :
   **flutter CLi**:

   flutter pub get

---

## 📂 Directory Structure

```
├── assets/             # Contains static resources (images, icons,sounds)
│   ├── images/
│   ├── icons/
│   ├── sounds/
├── doc/                # Project documentation files
├── lib/                # Main application code
│   ├── config/         # app Configuration (app routes , theme , services)
│   ├── model/          # Data models
│   ├── repositories/   # Data access logic (API, database)
│   ├── utils/          # Helper functions and utilities
│   ├── view/           # UI components and screens
│   └── main.dart       # App entry point
├── android/            # Android-specific code
├── ios/                # iOS-specific code
├── pubspec.yaml        # Flutter dependency configuration
└── README.md           # Project documentation
```
