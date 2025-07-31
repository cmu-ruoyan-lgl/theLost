# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**The Lost** is a narrative-driven visual novel exploring the theme of "loss" through the perspectives of six characters experiencing different types of trauma and grief. Players assume the role of a lost ghost who can observe and interact with these characters' memories and emotional states.

## Development Environment

This is a Unity 2021.3 LTS project for game development, with integrated AI content generation workflows using ComfyUI and Stable Diffusion XL.

### Required Unity Setup
- **Engine**: Unity 2021.3 LTS  
- **Render Pipeline**: Universal Render Pipeline (URP)
- **Essential Packages**: URP, Cinemachine, Timeline, TextMesh Pro
- **Key Dependencies**: 
  - Yarn Spinner (dialogue system)
  - DOTween Pro (animation)
  - Fungus (dialogue framework)

### AI Content Generation
- **Tool**: ComfyUI with Stable Diffusion XL
- **Workflows**: Located in `/comfyui/` directory
- **Purpose**: Generate character memory fragments and conceptual art

## Project Architecture

### Core Systems
- **Ghost Mechanics**: Player interaction system for non-corporeal movement and observation
- **Memory Fragments**: Collectible system that unlocks character backstories  
- **Emotion System**: Dynamic visual effects driven by character emotional states
- **Narrative Framework**: Yarn Spinner + Unity Timeline for branching dialogue and cutscenes
- **Localization**: Multi-language support (EN/ZH-CN/JP) via JSON files

### Character Structure
The game features 6 main characters, each representing different types of loss:
1. **Asher** - Military veteran who lost his daughter
2. **Lena** - Memory loss patient  
3. **Kai** - Composer who lost his musical dreams
4. **Maya** - Athlete who lost her health
5. **Elias** - Artist who lost his identity
6. **Sophie** - Journalist who lost trust

### Scene Organization
- **Prologue.unity** - Game introduction
- **Character Story Scenes** - Individual character narratives (6 scenes)
- **Memory Spaces** - Surreal environments for flashback sequences

## Development Guidelines

### Content Sensitivity
- Game deals with sensitive themes (suicide, abuse, trauma)
- Implement content warning system with double confirmation
- Include mental health resource links
- Use `ShowContentWarning(string theme)` method for sensitive scenes

### Dynamic Narrative System
- Emotion analysis affects pacing: `AnalyzePlayerChoices()` adjusts timeline speed
- Environmental storytelling through character living spaces
- Non-linear grief representation - no "correct" way to process loss

### AI Integration Workflow
1. Unity scene requirements → ComfyUI workflow
2. Content generation and review process  
3. Asset import and scene integration
4. Quality assurance for thematic consistency

### Asset Standards
- **Character Art**: 2048x2048 PNG with Spine animation
- **Memory Fragments**: 512x512 semi-transparent PNG with glow channels
- **Environment**: 2048x2048 PBR textures
- **Audio**: Ambient BGM at 44.1kHz/24bit, ASMR-quality voice recording

## Code Conventions

### C# Scripting Structure
```
Scripts/
├─ Core/           # Core game systems
├─ UI/             # User interface components  
├─ Interactions/   # Player interaction handlers
```

### Key Code Patterns
- Use Timeline for cutscene control
- Implement emotion-driven shader effects via Shader Graph
- JSON-based save system with AES encryption for multiple playthroughs
- Content warning integration for sensitive material

## File Organization

- `/game/` - Unity project files (currently empty - project in planning phase)
- `/comfyui/` - AI workflow configurations  
- `/design/` - Game design documents and character references
- `/readme.md` - Main project documentation (Chinese)

## Development Status

Project is in **pre-production phase**. Core documentation and design are complete, but Unity project structure and implementation are pending.