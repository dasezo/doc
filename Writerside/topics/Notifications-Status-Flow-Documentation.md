# Notifications Status Flow Documentation

---

## Overview

This document outlines all notification status-flow when the server sends notifications via socket to clients (web & mobile) to understand the exact state of a notification in the delivery process. The statuses include:

- **Undelivered**: Notification marked failed to reach the recipient's device by default.
- **Delivered**: Notification successfully delivered to the recipient's device.
- **Seen**: Notification was opened or displayed on the recipient's device (not necessarily read).
- **Read**: Notification was explicitly interacted with or marked as read by the recipient.

---

### Notification Status Flow

1. **Undelivered**:
    - Notification fails due to a network issue, app uninstallation device.
    - System to retry delivery within a client reconnection automatically.
2. **Delivered**:[how_notification_work_doc.md](How-Notification-Works.md)
    - Notification is pushed to the recipient's device (received in socket, and the developer changed its status to **delivred** ).
3. **Seen**:
    - when the user tapped notification icon or bill
    - Notification is opened or displayed via notification inbox.
    - or when the user unread a notification, it reverts it to see.
4. **Read**:

    - User interacts with the notification (e.g., clicks on it or marks it as read).

### Technical resumed requirements:

- **Backend**:

    - REST API or Restful endpoints for updating and retrieving notification statuses.
    - WebSocket or for real-time notification send.
    - Logging and retry mechanisms for "Undelivered" status.

- **Frontend**:
    - integrate socket.io in client side project and submitted to notification event.
    - Visual representation of statuses in the app (ex: badged notification icon, make diff notification tile colors ).
    - get delivred notification count to present it in the user UI.

**Note**: look at the diagrams attached to get more details.

### Notification Flow Diagram

<img src="notification-status-flow.png" alt="flow diagram" height="750" thumbnail="true" />
