# How Notification Works


---

## Overview
This document outlines all scenarios where the server sends notifications via socket,
including examples of message payloads.

---
## Note for Developers :

to trigger this above scenario, you should listen to Socket.io event "notification"

```code
socket.on('notification', (data) {
    //hundle your logic here  
});
```

---
## 1. Feedback Creation
### Trigger
The server sends this notification when a new feedback entry is created.

*Note: The notification will be sent to the user who created the task through which this Feedback was created.*

---

### Payload Example
The following JSON structure represents the notification payload:

```json
{
  "entity": "feedback",
  "title": "newFeedback",
  "data": {
    "id": 29,
    "missionId": 150
  },
  "creatorId": 10,
  "id": 1166,
  "creator": {
    "id": 10,
    "username": "newUser",
    "isActive": false,
    "roleId": 5,
    "annexId": 1,
    "companyId": 2,
    "person": {
      "id": 5,
      "firstName": "John",
      "lastName": "Doe",
      "email": "johndoe@example.com",
      "phone": "123-456-7890",
      "phone02": "098-765-4321",
      "address": "123 Main St",
      "gender": true,
      "img": "profile.jpg",
      "userId": 10,
      "createdAt": "2024-01-01T00:00:00.000Z",
      "updatedAt": "2024-01-02T00:00:00.000Z"
    },
    "iat": 1737387200
  }
}
```

## 2. Mission Assignment

### Trigger
The server sends this notification when a user is assigned to a new mission.

*Note: The `mission` assignment is only for `delegated` users.*
#### Payload Example

```json 
{
  "entity": "mission",
  "title": "newMission",
  "data": {
    "id": 1,
    "companyId": 1,
    "annexId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```

## 3. **Mission Status Change:**
### Trigger

The server sends this notification when the status of a mission changes.

*Note: The notification will be sent to the `user` who created the mission for the first time.*

---
### Payload Example
The following JSON structure represents the notification payload:

```json 
{
  "entity": "mission",
  "title": "newMission",
  "data": {
    "id": [1],
    "companyId": 1,
    "annexId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```

## 2. Mission Assignment

### Trigger
The server sends this notification when a user is assigned to a new mission.

*Note: The `mission` assignment is only for `delegated` users.*
#### Payload Example

```json 
{
  "entity": "mission",
  "title": "newMission",
  "data": {
    "id": 1,
    "companyId": 1,
    "annexId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```

### **Special Mission Scenario :**
The server can send a notification that holds a List /single data object, so be careful how to use this make your custom logic
---
### Payload Example
The following JSON structure represents the notification payload:

```code 
**List data object exmaple** 
{
  "entity": "mission",
  "title": "newMission",
  "data":[ {
    "id": [1],
    "companyId": 1,
    "annexId": 1
  }, {
    "id": [2],
    "companyId": 2,
    "annexId": 2
  }],
  ...
}
--------------------------------------
**single data object exmaple** 
{
  "entity": "mission",
  "title": "newMission",
  "data": {
    "id": [1],
    "companyId": 1,
    "annexId": 1
  },
  ...
}
```
-------------------------------------------

### 4. **Task Assignment as Responsible:**

#### Trigger

The server sends this notification when a user is assigned to a new task as Responsible.

---

### Payload Example
The following JSON structure represents the notification payload:

```json 
{
  "entity": "task",
  "title": "newTask",
  "data": {
    "id": 1,
    "missionId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```
**Field Explanations:**
- `data.id`: Mission ID (unique identifier for the mission)
- `data.missionId`: Associated mission ID for the task

### 5. **Task Assignment as Observer:**

#### Trigger

The server sends this notification when a user is assigned to a new task as an observer.

#### Payload Example

```json 
{
  "entity": "task",
  "title": "newTask",
  "data": {
    "id": 1,
    "missionId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```

### 5. **Task Status Change:**

#### Trigger

The server sends this notification when the status of a task changes.

```json 
{
  "entity": "task",
  "title": "newTask",
  "data": {
    "id": 1,
    "missionId": 1
  },
  "creatorId": 1,
  "id": 1166,
  "creator": {
    "id": 1,
    "username": "superAdmin",
    "isActive": true,
    "roleId": 1,
    "annexId": null,
    "companyId": null,
    "person": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": null,
      "phone": null,
      "phone02": null,
      "address": null,
      "gender": null,
      "img": null,
      "userId": 1,
      "createdAt": "2024-11-21T13:49:34.000Z",
      "updatedAt": "2024-11-21T13:49:34.000Z"
    },
    "iat": 1735745205
  }
}
```