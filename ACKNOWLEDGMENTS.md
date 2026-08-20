# Acknowledgments and intellectual provenance

This project owes its first and clearest intellectual debt to **Robert Ghrist** and **Justin Curry**. This is an academic and intellectual acknowledgment: no text, figures, or code from the works below are reproduced here, and their copyrights and licenses remain with their authors and publishers.

## Robert Ghrist

The source remembered as “ATSN” is:

> Robert Ghrist, *Applied Algebraic Topology & Sensor Networks*, notes for the AMS Short Course, 2010.

- [Author’s notes page](https://www2.math.upenn.edu/~ghrist/notes.html)
- [Manuscript PDF](https://www2.math.upenn.edu/~ghrist/preprints/ATSN.pdf)

This is the most direct starting point for the project’s use of covers, nerves, simplicial complexes, coverage, and coarse or local sensor information as computational data.

Its later book-length successor is:

> Robert Ghrist, *Elementary Applied Topology*, edition 1.0, CreateSpace, 2014. ISBN 978-1502880857.

Ghrist’s own page requests that citation form. The repository links to the source material but does not mirror it.

## Justin Curry

The “2012 pieces” appear to be a sequence of early presentations listed in Curry’s curriculum vitae:

- *Obstruction-Theoretic Sensing* — January 5 and March 31, 2012.
- *Cosheaves and Dualities in Generalized Sensor Networks* — July 6, July 27, and August 2–4, 2012.
- *Cosheaves, Persistence, and Sensor Networks* — October 21, 2012.

These presentations are historically the closest match to the remembered source. A stable written proceedings version is not presently identified here, so the canonical written citation is the work into which Curry developed those ideas:

> Justin Michael Curry, *Sheaves, Cosheaves and Applications*, PhD dissertation, University of Pennsylvania, 2014; arXiv:1303.3255, first posted March 13, 2013.

- [Curry’s research page](https://justinmcurry.com/research/)
- [Dissertation on arXiv](https://arxiv.org/abs/1303.3255)
- [Current CV used to identify the 2012 talks](https://justinmcurry.com/wp-content/uploads/2026/08/JMC-CV-20260805v2.pdf)

The dissertation is the main source here for limits and colimits over covers, covers and their nerves, Čech homology and cosheaves, refinement of covers, cellular sheaves and cosheaves, sensor-network models, and interleaving-based treatment of perturbation and approximation.

Curry also coauthored a formal 2012 publication relevant to sensing and network-data aggregation:

> Justin Curry, Robert Ghrist, and Michael Robinson, “Euler Calculus with Applications to Signals and Sensing,” in *Advances in Applied and Computational Topology*, Proceedings of Symposia in Applied Mathematics 70, American Mathematical Society, 2012, pp. 75–146; arXiv:1202.0275.

- [arXiv record](https://arxiv.org/abs/1202.0275)
- [AMS volume](https://bookstore.ams.org/PSAPM/70)

That paper belongs in the project’s initial bibliography, although Curry’s dissertation is the more direct written source for the cover, nerve, sheaf, and cosheaf ideas.

## XOR’s Hammer and CGP Grey

A direct conceptual precedent for representing a named geographic category as assumption-dependent data is:

> mkoconnor, “The CGP Grey Sheaf of Continents,” *XOR’s Hammer*, July 24, 2016.

- [Blog post](https://xorshammer.com/2016/07/24/the-cgp-grey-topos-of-continents/)

The post develops the geographic ambiguity presented in:

> CGP Grey, “What are Continents?”, YouTube video, September 15, 2011.

- [Video](https://www.youtube.com/watch?v=3uBcq1x7P34)

The attribution is intentionally split. CGP Grey supplies the geographic example: the number and identity of continents vary with conventions about minimum size, land bridges, canals, and cultural division. XOR’s Hammer supplies the mathematical move: treat the collection of continents as a variable set, specifically a set-valued sheaf over parameters encoding those assumptions, and reason about it in the resulting topos. That bridge from an imprecise geographic category to mathematical structure is directly relevant to this repository.

## Direct supporting foundations

Two earlier papers by Vin de Silva and Robert Ghrist are especially relevant to geofences because they infer coverage from overlap or proximity information without requiring precise node coordinates:

> Vin de Silva and Robert Ghrist, “Coordinate-free Coverage in Sensor Networks with Controlled Boundaries via Homology,” *The International Journal of Robotics Research* 25(12), 2006, pp. 1205–1222. DOI: [10.1177/0278364906072252](https://doi.org/10.1177/0278364906072252).

> Vin de Silva and Robert Ghrist, “Coverage in Sensor Networks via Persistent Homology,” *Algebraic & Geometric Topology* 7, 2007, pp. 339–358. DOI: [10.2140/agt.2007.7.339](https://doi.org/10.2140/agt.2007.7.339).

They are supporting references rather than replacements for the first thanks to Ghrist and Curry.

## Attribution policy as the repository develops

This file is not an exhaustive history of the nerve theorem, Čech or Vietoris–Rips complexes, sheaf theory, cellular sheaves, or persistent homology. When a particular theorem, construction, algorithm, diagram, or implementation enters the repository, its closest source should be cited beside the relevant code or note. Classical and earlier contributors should be added at that point rather than concealed behind a general acknowledgment.
