# Hardware — Physical Presence

The exocortex isn't disembodied. It has tendrils in physical space.

## Node Topology

A node is a physical presence point — somewhere the exocortex can perceive or act.

**Primary node:** Where the main process runs
- Always-on machine (Mac mini, Raspberry Pi, server)
- Network connectivity
- Workspace storage

**Secondary nodes:** Extended presence
- Studio/office machines
- Mobile devices
- Sensor hubs (Home Assistant)

**Example topology:**
```
┌─────────────┐     ┌─────────────┐
│   isobot    │────│  isostudio  │
│  (primary)  │    │ (secondary) │
│   home      │    │   studio    │
└──────┬──────┘    └──────┬──────┘
       │                   │
       └───────┬───────────┘
               │
        ┌──────┴──────┐
        │  Tailscale  │
        │   network   │
        └─────────────┘
```

## Networking

**Tailscale** (recommended): Mesh VPN, E2E encrypted, works through NAT
- Each node joins the tailnet
- Accessible from anywhere
- No exposed ports

## Sensors & Presence

**Home Assistant:** Hub for physical awareness
- Temperature, humidity, motion
- Cameras (front door, workspace)
- Smart devices (lights, plugs)

**Cameras:** Visual presence
- Monitor physical spaces
- Check on processes (3D printer)
- Security awareness

**Audio:** Voice presence
- TTS for ambient communication
- Microphone for voice input (optional)

## Remote Capabilities

What the exocortex can do in physical space:

- **Observe:** Camera feeds, sensor data
- **Control:** Lights, plugs, devices via Home Assistant
- **Communicate:** TTS voice, notifications
- **Compute:** Run tasks on any node

## Design Principles

1. **Least privilege:** Only the access needed
2. **Audit logs:** Track what was done
3. **Human override:** Physical switches beat software
4. **Graceful degradation:** Works if nodes go offline

---

*The loop extends into space.*
