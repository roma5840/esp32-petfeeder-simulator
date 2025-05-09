# ESP32 Pet Feeder Firebase Simulator

**Version:** 1.0

**Date:** May 9, 2025

**Target Application Code Version:** Designed for use with `app/petfeeder/index.tsx` as of version 8.2

## Temporary Firebase Security Rules for Testing

**IMPORTANT: These rules are for TESTING PURPOSES ONLY.**

```json
{
  "rules": {
    "users": {
      "$uid": {
        // .read and .write are the original rules
        ".read": "auth != null && auth.uid === $uid",
        ".write": "auth != null && auth.uid === $uid",
        "feederStatus": {
          ".read": true,
          ".write": true
        },
        "commands": {
          "feedNow": {
            ".read": true,
            ".write": true
          }
        },
        "feedingHistory": {
          ".read": "auth != null && auth.uid === $uid",
          ".write": true
        },
        "schedules": {
          ".read": true,
          ".write": "auth != null && auth.uid === $uid"
        }
      }
    }
  }
}
```

## Note

**This simulator is designed to reflect the Firebase interactions of the mobile application (`app/petfeeder/index.tsx`) as of its target version (see top of README).**