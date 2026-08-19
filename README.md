# geofence

Experiments in treating physical locations and geofences as imprecise, cover-based data rather than only exact latitude/longitude pairs.

A phrase such as “Ypsilanti, Michigan” usually denotes a region at a useful scale, not a point. This repository will explore representations that preserve uncertainty, overlap, refinement, containment, and local-to-global consistency. Candidate tools include covers and their nerves, Čech and Vietoris–Rips complexes, cellular sheaves and cosheaves, and explicit precision or refinement relations.

This is a research notebook, not yet a geofencing library. The first goal is to state the data model and operations before selecting an implementation language.

## Intellectual provenance

This project begins with Robert Ghrist’s work on applied algebraic topology and sensor networks, especially *Applied Algebraic Topology & Sensor Networks* (2010), and with Justin Curry’s early 2012 work on obstruction-theoretic sensing and cosheaves for generalized sensor networks, later developed in *Sheaves, Cosheaves and Applications* (arXiv 2013; PhD dissertation 2014).

Ghrist and Curry receive the first acknowledgment because the central approach explored here—organizing imprecise spatial observations through overlaps, covers, combinatorial topology, and local-to-global data—comes directly out of the mathematical territory they developed and explained.

See [ACKNOWLEDGMENTS.md](ACKNOWLEDGMENTS.md) for exact citations and for the distinction between Curry’s 2012 presentations and the stable written sources.

## Initial questions

- What is the type of a location whose resolution is part of the value?
- How should containment, overlap, ambiguity, and refinement be represented?
- When is a finite cover or its nerve a better representation than a point or polygon?
- What local data should glue, and what incompatibilities should remain visible?
- Which computations need ordinary GIS geometry, and which benefit from sheaf, cosheaf, or persistent-topology machinery?

## Status

Only scope and intellectual provenance are established. No API or implementation is claimed yet.
