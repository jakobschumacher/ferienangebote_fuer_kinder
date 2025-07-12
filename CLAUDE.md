# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML application that displays vacation program providers for children in Berlin. The application loads provider data from a CSV file and provides filtering and search functionality.

## Architecture

- **Frontend**: Single-page vanilla HTML/CSS/JavaScript application (`index.html`)
- **Data Source**: CSV file (`anbieter.csv`) containing provider information
- **Deployment**: Static hosting via GitHub Pages, loads CSV data dynamically from GitHub raw content

## Key Components

- **Data Loading**: CSV parser that fetches data from GitHub raw URL at runtime
- **Filtering System**: Multi-criteria filtering (category, district, age group, search text)
- **Provider Display**: Dynamic rendering of provider cards with details and contact information

## Development Environment

This project uses distrobox for isolated development:
- Launch development environment: `./launch-ferienangebote.sh`
- The distrobox container is named 'ferienangebote'
- Only the project directory is mounted in the container

## Data Structure

The `anbieter.csv` file contains provider information with columns:
- ID, Anbieter (Provider), Träger-Kategorie (Category), Trägerschaft (Ownership)
- Bezirk/Standort (District/Location), Zielgruppe (Target Group)
- Angebots-Typ (Offer Type), Kosten (Costs), Website/Kontakt (Website/Contact)
- Anmerkungen (Notes)

## Testing

Since this is a static HTML application:
- Test by opening `index.html` in a browser
- Verify CSV loading works by checking network requests
- Test filtering functionality manually through the UI
- No automated test framework is configured

## Key URLs

The application loads data from: `https://raw.githubusercontent.com/jakobschumacher/ferienangebote_fuer_kinder/refs/heads/main/anbieter.csv`