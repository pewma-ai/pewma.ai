# Pewma.ai Brownfield Architecture Document

## Introduction

This document captures the CURRENT STATE of the Pewma.ai landing page codebase, including its technical debt, workarounds, and real-world patterns. It serves as a reference for AI agents working on enhancements, specifically the upcoming deployment to GitHub Pages and the connection of the custom domain.

### Document Scope

Focused on the single `index.html` file provided, which constitutes the entire current system.

### Change Log

| Date | Version | Description | Author |
| --- | --- | --- | --- |
| Aug 9, 2025 | 1.0 | Initial brownfield analysis of the landing page. | Winston (Architect) |



## Quick Reference - Key Files and Entry Points

### Critical Files for Understanding the System

- **Main Entry**: `index.html` (Single file containing all structure, styling, and content).

## High Level Architecture

### Technical Summary

The Pewma.ai project is a single-page, static HTML landing page. It is self-contained, with all CSS styles embedded directly within the `<style>` tags in the document's `<head>`. The architecture is intentionally minimalist, designed for clarity, performance, and ease of deployment on static hosting platforms. It utilizes modern HTML5, CSS variables for theming, and keyframe animations for subtle user engagement. It has no JavaScript dependencies, which simplifies maintenance and maximizes loading speed.

### Actual Tech Stack (from `index.html` analysis)

| Category | Technology | Version/Details | Notes |
| --- | --- | --- | --- |
| Structure | HTML5 | `<!DOCTYPE html>` | Standard, semantic HTML structure. |
| Styling | CSS3 | Embedded in `<style>` | Uses CSS variables (Custom Properties) for theming. |
| Responsiveness | CSS Media Queries | `@media (max-width: 768px)` | A single breakpoint is used to adapt for mobile devices. |
| Fonts | Google Fonts | `Merriweather` (300, 400, 700) | External dependency fetched from `fonts.googleapis.com`. |
| Animations | CSS Keyframes | `@keyframes fadeInUp`, `@keyframes fadeIn` | Used for entry animations to enhance user experience. |
| Dependencies | None | N/A | The project has no JavaScript or build-tool dependencies. |



### Repository Structure Reality Check

- **Type**: Single File Project.
- **Package Manager**: None.
- **Notable**: The entire application is encapsulated in one file, which is ideal for a simple static site but will require structure if functionality grows.

## Source Tree and Module Organization

### Project Structure (Actual)

Plaintext

`pewma.ai/
└── index.html`

### Key Modules and Their Purpose

The document is semantically divided into the following sections using standard HTML tags:

- **`<header>`**: Contains the logo (`<h1>`) and tagline (`<p>`).
- **`<section>`**: Multiple `section` tags are used to segment the content logically (Intro, Principles, The Beginning).
- **`<div class="cta">`**: A dedicated container for the final Call to Action, including a mailto link.

## Data Models and APIs

- **Data Models**: None. The content is static and hardcoded into the HTML.
- **API Specifications**: None. The project does not interact with any backend APIs.

## Technical Debt and Known Issues

- **No Technical Debt**: For its intended purpose, the project is clean and efficient.
- **Potential Issue**: The use of a `mailto:` link for the call to action is simple but relies on the user having a configured email client. For a more robust solution, a future enhancement could involve a contact form integrated with a backend service.

## Integration Points and External Dependencies

- **Google Fonts**: The only external dependency is the font stylesheet loaded from `fonts.googleapis.com`. If this service were to fail, the browser would fall back to a default serif font.

## Development and Deployment

### Local Development Setup

1. No special setup is required.
2. Open the `index.html` file in any modern web browser to view the page.

### Build and Deployment Process

- **Build Command**: None. No build process is necessary.
- **Deployment**: Manual upload of the `index.html` file to a static web host.

## Testing Reality

- **Current Test Coverage**: None.
- **Testing Approach**: Manual visual verification across different browser sizes (desktop and mobile) is sufficient for this stage.