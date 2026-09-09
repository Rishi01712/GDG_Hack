# ShadowData

### Privacy & Permission Abuse Detection Android Application

ShadowData is an Android application designed to help users understand, monitor, and control how installed applications access sensitive device resources such as the camera, microphone, location, and contacts.

The application combines real-time privacy monitoring, permission analysis, explainable risk assessment, and on-device AI to provide users with a clear understanding of potential privacy threats.

The entire system is designed around privacy-first principles, with processing performed locally on the device and without sending personal data to external servers.

---

# Problem Statement

Modern Android applications often require access to sensitive device resources such as:

- Camera
- Microphone
- Location
- Contacts
- Other protected permissions

While Android provides permission controls, the permission names and technical information can be difficult for normal users to understand.

Users may therefore have difficulty identifying:

- Which applications have sensitive permissions
- Which applications are over-permissioned
- When sensitive resources are being accessed
- Whether an application represents a potential privacy risk
- What a particular Android permission actually allows
- Whether suspicious activity is occurring in the background

ShadowData addresses this problem by providing a centralized privacy-monitoring and risk-analysis system.

---

# Solution

ShadowData continuously analyzes application permissions and sensitive-resource activity and presents the results through a user-friendly Android interface.

The overall workflow is:

    Installed Applications
            │
            ▼
    Permission Collection
            │
            ▼
    Permission Analysis
            │
            ├───────────────┐
            ▼               ▼
    Permission Risk     Resource Access
       Analysis             Monitoring
            │               │
            └───────┬───────┘
                    ▼
             AI Risk Analysis
                    │
                    ▼
          SAFE / SUSPICIOUS / DANGEROUS
                    │
                    ▼
             User Dashboard
                    │
          ┌─────────┼─────────┐
          ▼         ▼         ▼
       Alerts    Incidents   Reports

---

# Key Features

## Real-Time Privacy Monitoring

ShadowData monitors access to sensitive device resources such as the:

- Camera
- Microphone

The dashboard displays the current privacy status and alerts users when sensitive resources are accessed.

This allows users to identify potentially unexpected access without manually checking application permissions.

---

# Privacy Mode

ShadowData includes a dedicated Privacy Mode, also referred to as Women Safety Mode.

The mode is designed for proactive privacy protection.

It provides:

- Camera access protection
- Microphone access protection
- Detection of unauthorized access attempts
- Immediate privacy alerts

The objective is to provide an additional layer of awareness when the user wants sensitive device resources to remain protected.

---

# AI-Based Risk Prediction

ShadowData uses on-device AI to classify applications according to their potential privacy risk.

Applications are classified into three categories:

    SAFE
      │
      ├── Normal permission usage
      │
      ▼
    SUSPICIOUS
      │
      ├── Potentially concerning permission usage
      │
      ▼
    DANGEROUS
      │
      └── High-risk permission/activity profile

The predictions are performed locally on the Android device using TensorFlow Lite.

No cloud-based inference is required for the risk classification.

---

# AI / ML WORKFLOW

The AI pipeline converts application permission information into an understandable privacy-risk classification.

The complete conceptual workflow is:

    Installed Application
            │
            ▼
    Application Permission Data
            │
            ▼
    Permission Feature Extraction
            │
            ▼
    Feature Representation
            │
            ▼
    TensorFlow Lite Model
            │
            ▼
    On-Device Inference
            │
            ▼
    Risk Classification
            │
       ┌────┼────┐
       ▼    ▼    ▼
     SAFE  SUSPICIOUS  DANGEROUS
            │
            ▼
      Risk Explanation
            │
            ▼
       User Dashboard

---

# Permission Analysis

The application examines permissions associated with installed applications.

Instead of exposing only technical Android permission identifiers, ShadowData converts them into simpler explanations.

For example, the system can explain that a permission provides an application with access to a sensitive resource instead of requiring the user to understand Android's internal permission terminology.

This improves privacy awareness for non-technical users.

---

# Permission Feature Extraction

Permission information can be represented as features for the AI risk-analysis pipeline.

Conceptually:

    Application
        │
        ▼
    Permissions
        │
        ├── Camera
        ├── Microphone
        ├── Location
        ├── Contacts
        └── Other Sensitive Permissions
        │
        ▼
    Permission Feature Vector
        │
        ▼
    AI Model

The resulting representation allows the on-device model to evaluate an application's permission profile.

---

# Risk Classification

The AI system produces one of three primary risk categories:

| Risk Level | Meaning |
|------------|---------|
| SAFE | Application does not exhibit a significant privacy-risk profile |
| SUSPICIOUS | Application has permission characteristics that may require user attention |
| DANGEROUS | Application presents a high-risk privacy profile |

The classification is displayed directly to the user through the application interface.

---

# On-Device AI

One of the major design decisions of ShadowData is that AI inference is performed locally.

    Application Data
          │
          ▼
    Feature Processing
          │
          ▼
    TensorFlow Lite
          │
          ▼
    Local Inference
          │
          ▼
    Risk Classification

This approach avoids sending application permission information to an external AI service.

Benefits include:

- Improved privacy
- Reduced network dependency
- Local inference
- Lower data exposure
- Offline operation
- Edge AI architecture

---

# Privacy-First Architecture

ShadowData follows a privacy-first design philosophy.

The repository specifies that:

- No audio is recorded
- No video is recorded
- Personal data is not collected
- Data is not sent to external servers
- Processing is performed locally
- AI inference runs on-device

The application is therefore designed to monitor privacy without becoming another source of privacy exposure.

---

# Installed App Analysis

ShadowData provides an overview of applications installed on the device.

For each application, users can access information such as:

- Application identity
- Risk classification
- Permission information
- Sensitive permission usage
- Risk explanation

The system also highlights potentially over-permissioned applications.

---

# Application Detail Analysis

Users can select an individual application to inspect its privacy profile.

The application detail view provides:

- Permission breakdown
- Risk classification
- Permission explanations
- Privacy-risk information

This makes it easier to understand why an application may have been classified as SAFE, SUSPICIOUS, or DANGEROUS.

---

# Alerts & Incident Logging

ShadowData records high-risk privacy events and maintains an incident timeline.

The monitoring system can record events associated with sensitive-resource access and privacy violations.

The workflow is:

    Sensitive Resource Access
              │
              ▼
        Event Detection
              │
              ▼
       Risk Evaluation
              │
              ▼
        Alert Generation
              │
              ▼
       Incident Logging
              │
              ▼
        Incident Timeline

This gives users a historical view of privacy-related events instead of relying only on real-time notifications.

---

# Reports & Export

ShadowData supports exporting privacy-monitoring information for reporting and evaluation.

Supported formats include:

- CSV
- PDF

This allows users to preserve incident information and analyze privacy events later.

---

# Dashboard

The main dashboard provides a centralized view of the device's privacy state.

The dashboard includes:

- Current privacy status
- Sensitive-resource monitoring
- Application risk information
- Privacy alerts
- Monitoring controls

The objective is to provide users with a simple overview without requiring them to navigate through multiple Android settings screens.

---

# Multi-Theme Support

ShadowData supports multiple visual themes.

Available themes include:

- Light Theme
- Dark Theme
- Green Security Theme

Themes dynamically affect:

- Backgrounds
- Cards
- Text
- Controls
- Other interface elements

---

# System Architecture

    ┌───────────────────────────────┐
    │       Android Device         │
    └───────────────┬───────────────┘
                    │
                    ▼
    ┌───────────────────────────────┐
    │      Installed Applications    │
    └───────────────┬───────────────┘
                    │
                    ▼
    ┌───────────────────────────────┐
    │       Permission Analysis     │
    │                               │
    │  Camera                       │
    │  Microphone                   │
    │  Location                     │
    │  Contacts                     │
    │  Other Permissions             │
    └───────────────┬───────────────┘
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
    ┌───────────────┐   ┌────────────────┐
    │ Resource      │   │ Permission     │
    │ Monitoring    │   │ Feature        │
    │               │   │ Extraction     │
    └───────┬───────┘   └───────┬────────┘
            │                   │
            │                   ▼
            │          ┌────────────────┐
            │          │ TensorFlow     │
            │          │ Lite Model     │
            │          └───────┬────────┘
            │                  │
            │                  ▼
            │          ┌────────────────┐
            │          │ Risk           │
            │          │ Classification │
            │          └───────┬────────┘
            │                  │
            └─────────┬────────┘
                      ▼
             ┌──────────────────┐
             │ Privacy Analysis │
             └────────┬─────────┘
                      │
             ┌────────┼─────────┐
             ▼        ▼         ▼
          Dashboard Alerts   Incidents
                               │
                               ▼
                            Reports

---

# End-to-End Workflow

The complete ShadowData workflow can be summarized as:

    1. Discover installed applications
                    ↓
    2. Collect application permission information
                    ↓
    3. Analyze sensitive permissions
                    ↓
    4. Convert permissions into understandable explanations
                    ↓
    5. Extract relevant permission features
                    ↓
    6. Pass features to TensorFlow Lite
                    ↓
    7. Perform on-device AI inference
                    ↓
    8. Classify application risk
                    ↓
    9. Monitor sensitive-resource activity
                    ↓
    10. Detect privacy-related events
                    ↓
    11. Generate alerts
                    ↓
    12. Store incident information
                    ↓
    13. Display results on dashboard
                    ↓
    14. Export reports when required

---

# Application Architecture

The application follows an Android architecture based on:

- Single Activity
- Modular Composables
- Jetpack Compose
- Material 3
- Navigation Component
- On-device TensorFlow Lite inference

The UI is divided into functional screens and components rather than relying on a single large interface.

---

# Application Screens

## Main Dashboard

Provides:

- Live privacy overview
- Current privacy status
- Monitoring controls
- Security information

## App List

Displays:

- Installed applications
- Risk indicators
- Application-level privacy information

## App Detail

Provides:

- Permission breakdown
- Risk classification
- Permission explanations
- Privacy analysis

## Alerts & Incidents

Displays:

- Privacy alerts
- Detected incidents
- Historical event timeline
- Export options

## Settings

Provides:

- Theme selection
- Application preferences
- Privacy-related controls

## About

Provides:

- Project information
- Privacy principles
- Application details

---

# Technology Stack

## Android

- Kotlin
- Android SDK
- Jetpack Compose
- Material 3
- Jetpack Navigation Component

## Architecture

- Single-Activity Architecture
- Modular Composables

## AI / ML

- TensorFlow Lite
- On-device Machine Learning
- Edge AI
- Local inference

## Privacy & Security

- Local processing
- Permission analysis
- Sensitive-resource monitoring
- Incident logging

---

# Google AI Technologies

ShadowData uses:

- TensorFlow Lite
- On-device Machine Learning
- Edge AI

The use of TensorFlow Lite allows the application to perform model inference directly on the Android device rather than requiring a remote AI server.

---

# Project Structure

    GDG_Hack/
    │
    ├── .idea/
    │
    ├── app/
    │   └── Android application source
    │
    ├── gradle/
    │
    ├── .gitignore
    ├── build.gradle.kts
    ├── gradle.properties
    ├── gradlew
    ├── gradlew.bat
    ├── settings.gradle.kts
    └── README.md

---

# Requirements

To build and run ShadowData, you need:

- Android Studio
- Android SDK
- Kotlin
- Gradle
- Android device or emulator

For accurate real-time privacy monitoring, running the application on a physical Android device is recommended.

---

# Example Workflow

A typical user workflow looks like:

    Open ShadowData
          │
          ▼
    View Privacy Dashboard
          │
          ▼
    Scan Installed Applications
          │
          ▼
    Select an Application
          │
          ▼
    View Permissions
          │
          ▼
    AI Risk Classification
          │
          ▼
    SAFE / SUSPICIOUS / DANGEROUS
          │
          ▼
    Understand Permission Risks
          │
          ▼
    Monitor Sensitive Activity
          │
          ▼
    Receive Alerts
          │
          ▼
    Review Incident History
          │
          ▼
    Export Report

---

# Why ShadowData Stands Out

## 1. Combines Privacy + AI

ShadowData combines:

    Android Permissions
            +
    Real-Time Monitoring
            +
    Machine Learning
            +
    Explainability
            +
    Incident Detection

This creates a complete privacy-awareness platform rather than a simple permission viewer.

---

## 2. On-Device Intelligence

The AI model runs locally using TensorFlow Lite.

This means application risk analysis does not require sending permission information to an external AI service.

---

## 3. Explainable Privacy Analysis

Instead of presenting users with only technical permission names, ShadowData explains what permissions mean and why they may represent a privacy concern.

---

## 4. Real-Time Monitoring

The application does not only inspect permissions statically.

It also monitors sensitive-resource activity and can alert users when camera or microphone access occurs.

---

## 5. Privacy-First Design

The monitoring system itself is designed to avoid collecting or transmitting personal data.

The application is intended to improve privacy awareness without compromising the user's privacy.

---

# Future Improvements

Potential future improvements include:

- More advanced permission-risk models
- Application behavior analysis
- Permission-access frequency analysis
- Temporal anomaly detection
- More detailed risk explanations
- Risk-score confidence values
- Historical risk trends
- Additional sensitive-resource monitoring
- Automated privacy recommendations
- More advanced incident correlation
- Application-level privacy scoring
- Improved model explainability
- Expanded Android-version compatibility

---

# Project Objective

ShadowData aims to make Android privacy easier to understand and monitor.

The primary objectives are:

- Improve awareness of permission misuse
- Identify potentially risky applications
- Monitor sensitive-resource access
- Provide explainable privacy insights
- Detect and log privacy incidents
- Provide on-device AI-based risk prediction
- Preserve user privacy through local processing

The overall goal is to transform complex Android permission information into simple, actionable privacy intelligence.

---

# Privacy Principles

ShadowData follows these core principles:

    Local First
        ↓
    Process information on-device

    Privacy First
        ↓
    Avoid unnecessary data collection

    Explainability
        ↓
    Make technical permissions understandable

    User Awareness
        ↓
    Clearly communicate potential risks

    Responsible AI
        ↓
    Use AI for privacy analysis without
    unnecessarily exposing user data

---

# Disclaimer

ShadowData is a research and educational project.

It is designed to provide privacy awareness, permission analysis, and risk insights.

It does not bypass Android security policies and does not intentionally collect personal user data.

Risk classifications should be treated as security-awareness indicators rather than definitive proof that an application is malicious.

* **Links**

  * **Deployment Link:** [https://docs.google.com/document/d/1HUMvIvHtCklXA_VM_p-Y7S8AifCmO9A2/edit?usp=drive_link&ouid=101882663731378130755&rtpof=true&sd=true](https://docs.google.com/document/d/1HUMvIvHtCklXA_VM_p-Y7S8AifCmO9A2/edit?usp=drive_link&ouid=101882663731378130755&rtpof=true&sd=true)
  * **Demo Link:** [https://drive.google.com/file/d/1Td27klUisj5VBaMfo19Dg8hVJDJ1erhH/view?usp=drive_link](https://drive.google.com/file/d/1Td27klUisj5VBaMfo19Dg8hVJDJ1erhH/view?usp=drive_link)

