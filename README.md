# geofence

Experiments in treating physical locations and geofences as imprecise, cover-based data rather than only exact latitude/longitude pairs.

A phrase such as “Ypsilanti, Michigan” usually denotes a region at a useful scale, not a point. This repository will explore representations that preserve uncertainty, overlap, refinement, containment, and local-to-global consistency. Candidate tools include covers and their nerves, Čech and Vietoris–Rips complexes, cellular sheaves and cosheaves, and explicit precision or refinement relations.

This remains a research notebook, not a complete geofencing library or Android application. The first experimental computational model is written in Idriç, now including a bounded circular-longitude and round-sphere quotient-cell experiment; ordinary GIS remains future work.

## Intellectual provenance

This project begins with Robert Ghrist’s work on applied algebraic topology and sensor networks, especially *Applied Algebraic Topology & Sensor Networks* (2010), and with Justin Curry’s early 2012 work on obstruction-theoretic sensing and cosheaves for generalized sensor networks, later developed in *Sheaves, Cosheaves and Applications* (arXiv 2013; PhD dissertation 2014).

Ghrist and Curry receive the first acknowledgment because the central approach explored here—organizing imprecise spatial observations through overlaps, covers, combinatorial topology, and local-to-global data—comes directly out of the mathematical territory they developed and explained.

A direct conceptual precedent on the geographic side is XOR’s Hammer’s [“The CGP Grey Sheaf of Continents”](https://xorshammer.com/2016/07/24/the-cgp-grey-topos-of-continents/), which takes CGP Grey’s [“What are Continents?”](https://www.youtube.com/watch?v=3uBcq1x7P34) and models the changing collection of continents as a set-valued sheaf. CGP Grey is credited for the geographic example and its shifting criteria; XOR’s Hammer is credited for the sheaf and topos formulation.

See [ACKNOWLEDGMENTS.md](ACKNOWLEDGMENTS.md) for exact citations and for the distinction between Curry’s 2012 presentations and the stable written sources.

## Initial questions

- What is the type of a location whose resolution is part of the value?
- How should containment, overlap, ambiguity, and refinement be represented?
- When is a finite cover or its nerve a better representation than a point or polygon?
- What local data should glue, and what incompatibilities should remain visible?
- Which computations need ordinary GIS geometry, and which benefit from sheaf, cosheaf, or persistent-topology machinery?

## Status

The first executable Idriç slice is experimental and deliberately narrow:

- [Geofence.Cover](idric/Geofence/Cover.idric): nonempty finite alternatives for an imprecise location, three-valued fence membership, cellwise cover refinement, and overlap. Geometry supplies the predicates rather than being silently replaced by coordinates.
- [Geofence.Latitude](idric/Geofence/Latitude.idric): validated nonempty closed latitude bands in degrees, using [intervals.idr](https://github.com/dilapidated-shed/intervals.idr) for exact containment and intersection. This is a one-dimensional chart-axis example, **not** a spherical or WGS84 region.
- [Geofence.Longitude](idric/Geofence/Longitude.idric): exact rational degrees modulo 360, nonempty closed circular arcs with a separate full-circle value, and exact arc containment/overlap across the antimeridian.
- [Geofence.Sphere](idric/Geofence/Sphere.idric): finite quotient patches on the **round topological sphere** (latitude band × circular arc, with longitude collapsed at each pole), retaining the same cover/refinement/three-valued membership operations.
- [Geofence.Check](idric/Geofence/Check.idric): compiler-checked fixtures for definitely inside, definitely outside, ambiguous boundary crossings, alternatives, latitude limits, refinement, longitude equivalence, antimeridian crossings and both poles.

The [acceptance workflow](.github/workflows/idric-geofence.yml) pins both Idriç and intervals.idr to exact commits. The interval implementation is checked out at build time; no second copy of interval semantics is kept here.

With an available Idriç compiler, a local source checkout can build the fixtures using:

```sh
git clone https://github.com/dilapidated-shed/intervals.idr.git .deps/intervals
git -C .deps/intervals checkout b3574ac06101f53a97c10839b420e656bd93bf46
ln -s ../.deps/intervals/idric/Interval idric/Interval
idris2 --build geofence-idric.ipkg
./build/exec/geofence-idric-tests
```

**Mathematical scope:** a closed arc from 0° to 360° is a *singleton* (both endpoints represent the same longitude); `all_longitudes` represents the entire circle. Circular endpoints are rational, not floating-point approximations. The spherical model identifies all longitudes **only at the poles**. The patches are quotient-images of closed coordinate rectangles, not general spherical regions. Inclusion and overlap are exact for this bounded model, with no spherical distance or geographic datum involved.

The current work does **not** implement arbitrary spherical polygons or oriented Jordan regions, WGS84/ellipsoid geometry, datum/chart transformations, GNSS measurement processing, Android geofencing registration, UI, or on-device execution. No Android behavior is claimed from a successful host-level Idriç test.
