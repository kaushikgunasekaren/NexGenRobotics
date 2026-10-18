# NexGenRobotics - Automated Glovebox Workflow

Built at Devils Invent: PU (Plutonium) Automations, an ASU hackathon with Los Alamos National Laboratory (March 2025).

This project automates a glovebox workflow for hazardous material reclamation and disposal: a robotic arm finds, picks, and moves material inside the glovebox as part of an automated pick-and-place routine.

**Role:** Programmer & Team Lead - Kaushik Gunasekaren

## What the software does

The main program, `Python Implement Final.py`, controls a Dobot Magician arm through Dobot's DLL API:

- **Computer vision (OpenCV):** captures the camera feed, detects the target object by color, and computes its offset from the image center using quadrant logic to align the arm over the object.
- **Ultrasonic sensing:** reads object height through the arm's EIO ports to set the pickup position.
- **Automated pick-and-place:** moves to a scan position, captures a frame, aligns on the detected object, grips it, and places it at the drop location.
- **Tkinter GUI:** live camera view with the detection overlay, plus controls to run the routine.

## Requirements

- Dobot Magician with gripper, connected over USB serial (115200 baud)
- Python 3 with `opencv-python` and `pyserial` (both vendored in this repo)
- Dobot DLLs (included in this repo)

## Repo notes

The Dobot API wrapper (`DobotDllType.py`) and DLLs come from Dobot's Python demo package. The hackathon code is `Python Implement Final.py`.
