# SentinelView 🔐📷  
**Cloud Security Camera Feed & Event Dashboard**

SentinelView is a SwiftUI-based iOS application that simulates a modern cloud security platform by aggregating live camera feeds, AI-generated event detections, and cloud-processed metadata into a single, responsive mobile experience.  

The project is designed to mirror real-world security systems such as Verkada, emphasizing **device-to-cloud architecture, concurrency, secure networking, and AI-driven insights**.

---

## 🚀 Motivation

Modern security platforms are no longer just passive camera systems. They rely on:
- cloud-based ingestion of device data
- real-time event processing
- AI-powered detection and search
- performant mobile clients

SentinelView was built to explore these systems end-to-end, from camera snapshot ingestion to event visualization on iOS, while practicing production-grade mobile and backend engineering patterns.

---

## 🧩 Core Features

### 📸 Live Camera Snapshots
- Fetches live image snapshots from public camera APIs
- Periodic refresh using **Swift concurrency (`async/await`)**
- Intelligent cancellation when views disappear
- Graceful error handling and offline fallback

### 🧠 AI-Generated Event Timeline
- Displays cloud-processed events such as:
  - motion detection
  - person or vehicle detection
  - environmental anomalies
- Reverse-chronological timeline optimized for quick scanning
- Event detail view with metadata, confidence scores, and timestamps

### 🎯 AI Detection Overlays
- Bounding boxes and labels rendered directly over camera images
- Supports backend-generated inference results (e.g. YOLO-style outputs)
- SwiftUI Canvas-based overlay rendering for performance

### 🌍 Multi-Camera Support
- Multiple camera locations and sources
- Configurable refresh intervals
- Persistent user selections using local storage

### 🔐 Secure Cloud Architecture
- Backend API proxy to prevent client-side API key exposure
- Token-based authentication
- Structured request/response schemas

---

## 🏗 Architecture Overview

