# What have I done with the code base

+++

## Motivation

- provide more classes
- Raa, Jpsi

- classical software problems (extension, correctness, stability)
  - extension were done through copy&paste of codebase + changes in new copy
  -> no common source code, no clear responsibilities, results in typical
  software engineering problems
  - possibility for other experiments to add masterclasses, without initial
  code investment

  - improve deployment process
 
+++

## Initial state

- 3 Masterclasses (Strangeness, Raa, J/Psi)
- Version from Christian Holm Christensen
- Repository hosted on gitlab.cern.ch
- integrate Raa and Strangeness in same repository, provide initial translation facilities
- packaged as Docker image
- dead project
- Screenshot of initial window (Class and Language Selection)

+++

## Translation

- Go from only HTML documents translated to full GUI translations
- easy to extend to new languages
- semi automatic translation possible with provided scripts around google translate
- consistency checking between english and all translations "are all strings provided?"
- how to add a new language, short demo / Screenshots
- German as first translation, Dutch WIP, Danish partially exists from prior
  work
- "Very Pleasant" ~ Redmer Alexander Bertens
- publicly available on gitlab => Every group can add translations to their
  native languages

+++

## Refactoring

- Refactoring = "Structural Changes of Code without affecting behaviour"
- Missing Unit Testing or Integration Tests => random breakage on changes of
  unrelated parts

- Codebase was not changeable, so Refactorings are necessary as first step
- every masterclass was copy&pasted from 'template' => doing the same task 3
  times to change something in the masterclasses
- new Design to adhere to already formulated Goals (Extendability first)

UML Diagram to show, simplified

- SOLID  = "Single Responsibily, Open/Closed Principle, Liskov Substitution
  Prinicple, Interface Segregation Principle, Dependency Inversion Prinicple"

- adhere to SOLID as they give better theoretical and practical code properties
- TTrackCounter vs RaaCounter, RaaCalculator, RaaHistograms

- Amount of Code to provide a Masterclass before
- Amount of Code to provide a Masterclass after

+++

## How to use now

- ported to ROOT6 to be future prove
- compiled executable => Only start and set a data directory correctly, no
  other manual tasks required
- CMake based process, builds out of the box with just ROOT installed
- stability improved a lot
- all masterclasses in one package

+++

## Extend Raa after Refactoring

- prior critiscism was monotonic experience when selection primary tracks
- starting from prior work of student integrate different selection criteria
- show 4 properties that can be analyzed in an event
- distinguish between charges
- distinguish between primary and secondary particle
- estimate particle momentum from curvature
- more attractive and explains more physics

+++

## Integrated J/Psi Masterclass from GSI

- right now just a code dump
- you can run it and it is basically integrated, but code wise not updated
  to the new framework

+++

## Outlook

+++

## The Next week

- make the installation process super smooth
- AppImage shall be explored, meaning that would not require a ROOT
  installation
- otherwise works already good enough
- start refactoring J/Psi as well
- make all parts runnable again

+++

## For the next Student working on it

- js-ROOT-js provides basic event display support already
- [Example](https://root.cern.ch/js/latest/?nobrowser&json=../files/geom/simple_alice.json.gz&file=../files/geom/tracks_hits.root&item=simple_alice.json.gz+tracks_hits.root/tracks;1+tracks_hits.root/hits;1)
- there is not alternative to a Web-based Masterclass framework
- the basic architecture and structure can be reused
- new technologies like WebAssembly and Emscrippten allow C++ to be compiled to
  javascript => code reuse for the webbases framework

+++

## Summary

- refactored the codebase with extendability in mind
- provide full translation support for all ASCII-Represantable languages
- Make installation process smooth
- already extend some of the masterclasses
- integrate Strangenss, Raa and J/Psi into one executable
