# Leader-Follower-Drone
This project implements a Leader Drone Control System using DroneKit–Python and Firebase Realtime Database.

Features
📡 Real-Time Firebase Sync

Leader drone continuously uploads:

Latitude

Longitude

Altitude

Stored in /Leader_Location in the Firebase database.

🎮 Remote Command Execution

Listen for commands in /Leader_Control:

"takeoff" → Auto-takeoff to target altitude

"RTL" → Return-to-launch

(latitude, longitude) → Navigate to a waypoint

✈️ Autonomous Navigation

Uses DroneKit simple_goto()

Uses Haversine distance to validate arrival

Supports SITL (Software-In-The-Loop) and real Pixhawk hardware

🧵 Multi-Threading

Two threads run in parallel:

Location Upload Thread

Firebase Setup Guide

Follow these steps to correctly connect your drone code to Firebase:

Step 1: Create Firebase Project

Go to Firebase Console
https://console.firebase.google.com

Click Add Project → Create a new project

Disable Google Analytics (optional)

Step 2: Enable Realtime Database

From the left sidebar → Build → Realtime Database

Create Database → Start in Test Mode

Choose your region → Click Enable

Your database URL will look like:

https://leader-follower-default-rtdb.firebaseio.com/


Copy this — you need it in your code.

Step 3: Add Service Account Key

Go to
Project Settings → Service Accounts → Firebase Admin SDK

Select Python

Click Generate New Private Key

A JSON file will download:

leader-follower.json


Save it inside your project folder:

/home/biman/Desktop/swarm/leader-follower.json




Firmware Ardupilot

Command Listener Thread
