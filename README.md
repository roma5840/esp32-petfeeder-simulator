# ESP32 Pet Feeder Firebase Simulator

**Version:** 2.0

**Date:** May 10, 2025

**Target Application Code Version:** Designed for use with `app/petfeeder/index.tsx` as of version 9.

## Temporary Firebase Security Rules for Testing

**IMPORTANT: These rules are for TESTING PURPOSES ONLY.**

```json
{
  "rules": {
    "users": {
      "$uid": {
        ".read": "auth != null && auth.uid === $uid",
        ".write": "auth != null && auth.uid === $uid",
        "feederConfig": {
          ".read": true,
          ".write": true
        },
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