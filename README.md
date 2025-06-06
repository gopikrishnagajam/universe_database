# Universe Database

This PostgreSQL database models a simplified version of the known universe, including galaxies, stars, planets, moons, and comets. It is designed for educational and practice purposes (e.g., SQL queries, database design, and data relationships).

## Database Information

- **Database Name:** `universe`
- **Encoding:** UTF-8
- **Owner:** `freecodecamp`

---

## Schema Overview

The database consists of six main tables:

1. **galaxy**
2. **star**
3. **planet**
4. **moon**
5. **comet**
6. **Sequences** (for ID auto-incrementation)

---

## Tables and Relationships

### 🌌 Galaxy

Represents galaxies in the universe.

- **galaxy_id** (PK): Unique identifier
- **name** (UNIQUE): Name of the galaxy
- **age**: Age in billion years
- **has_black_hole**: Boolean flag
- **distance_from_earth**: Distance in light-years

### ☀️ Star

Represents stars, each belonging to a galaxy.

- **star_id** (PK): Unique identifier
- **name** (UNIQUE): Star name
- **galaxy_id** (FK): Links to `galaxy.galaxy_id`
- **temperature**: Temperature in Kelvin
- **is_sun**: Boolean flag for our Sun

### 🪐 Planet

Represents planets orbiting stars.

- **planet_id** (PK): Unique identifier
- **name** (UNIQUE): Planet name
- **star_id** (FK): Links to `star.star_id`
- **population**: Population on the planet
- **has_life**: Boolean flag

### 🌙 Moon

Represents moons orbiting planets.

- **moon_id** (PK): Unique identifier
- **name** (UNIQUE): Moon name
- **planet_id** (FK): Links to `planet.planet_id`
- **radius_km**: Radius in kilometers
- **is_tidal_locked**: Boolean flag

### ☄️ Comet

Represents comets flying through the universe.

- **comet_id** (PK): Unique identifier
- **name** (UNIQUE): Name of the comet
- **speed_kmh**: Speed in km/h
- **has_tail**: Boolean flag
- **discovered_by**: Name of the discoverer

---

## Relationships

- One **galaxy** can have many **stars**
- One **star** can have many **planets**
- One **planet** can have many **moons**
- **Comets** are standalone and do not link to other entities

---

## Example Data

- Galaxies: Milky Way, Andromeda, Sombrero
- Stars: Sun, Sirius, Vega
- Planets: Earth, Mars, Proxima b
- Moons: Luna, Phobos, Europa
- Comets: Halley's Comet, NEOWISE

---

## Getting Started

To use this database:

1. Restore the provided `.sql` dump using `psql`:
   ```bash
   psql -U postgres -f universe_dump.sql
