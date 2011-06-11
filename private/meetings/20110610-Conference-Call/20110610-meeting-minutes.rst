OBOE Ontology Extensions Meeting Agenda
=======================================
MINUTES
-------
+-------------------+----------------------------------------------------------+
|DATE               | June 10, 2011  1:00 pm PDT                               |
+-------------------+----------------------------------------------------------+
|TYPE OF MEETING    | Ontology Development                                     |
+-------------------+----------------------------------------------------------+
|CALL IN            | EVO_ (Password: oboe)                                    |
+-------------------+----------------------------------------------------------+
|NOTES              | Everyone on an ePad                                      |
+-------------------+----------------------------------------------------------+
|ATTENDEES          | Shawn Bowers, Ben Leinfelder, Chris Jones, Matt Jones,   |
|                   | Margaret O'Brien, Mark Schildhauer                       |
+-------------------+----------------------------------------------------------+

**Initial Agenda**

1. **Discussion of Spatial and Temporal class choices**

- See: Spatial-Temporal-Components.pdf_
- Ontology extensions need consistent classes for spatial and temporal concepts
- International standards provide low-level building blocks of these concepts
  ISO, OGC, FGDC, etc.
- Domains are expected to create application schemas that incorporate these   
  concepts into higher level concepts
- None provide OWL-based implementations NASA SWEET provides both, although less 
  comprehensively

2. **Which is more appropriate for integration into OBOE extensions?**

- SWEET
    - More domain relevant 
    - More complex relationships
    - Less consistent modeling
    - OWL syntax

- GML
    - Less domain relevant 
    - Less complex relationships
    - More consistent modeling
    - XML Schema syntax

- Adopting concepts from GML or SWEET namespaces may be fuzzy (copy to new ns, use separately), or defined as equivalent to the concept.

- Versioning of OBOE may be problematic if SWEET is adopted because of their versioning policy

- Annotations are defined in RDF Schema: 'isDefinedBy': used to provide a definition of a term (a special form of "seeAlso"). Also 'similarTo' may be useful.

- Certain areas of SWEET look to be more well defined, and others not.  It would be good to work with the ESIP community to help SWEET to evolve.

- OBOE classes could include annotations that refer to SWEET classes that 'didn't quite fit' and why.  This may be a reasonable paper topic.

- The problem of ontology alignment is not new, and we should try to address it within our domains of interest.

- What about partial alignment? It's not easy in the OWL framework.  The problem is where you have agreement among two communities of the concept of a 'watershed', but we don't have agreement on how that concept fits in to the larger concept map.  Part of the issue is the pragmattic expression of the differences in OWL.

- Less formal version of "equivalentClass" could be "inPrincipalEquivalentTo"

    - relatedTo
    - similarTo
    - sameConceptAs (different than sameClassAs)  ... maybe need a better name for this?
        - e.g., equivalentInPrinciple
        - or sameScopeAs

- We could potentially subclass SWEET classes, but we will still inherit superclass concepts.
    - e.g., if we define B, which is "isNotQuiteEquivalent" to C
        - One option: have B subclass C, but would make B inherit 
          superclasses of C
        - Could also define a more general class A and have B and C subclass A 
        - Could go further, and assert overlap 
            - Could share an instance
            - Could define an "overlap" class D (subclass of B intersect C)

**Decision**: In order to stay aligned with the O&M Model at the OGC, we will model space and time classes using the GML classes (informed by the O&M model too).  

**Decision**: Although SWEET provides higher level domain concepts, we are not fully in agreement with the concept relationships. Therefore, we will create equivalent higher-level concepts in OBOE and annotate them to show the FQDN of the related concept in SWEET.

**Action**: Annotations will go into oboe.owl

**Action**: Space and Time classes will go into oboe.owl


.. _Spatial-Temporal-Components.pdf: https://code.ecoinformatics.org/code/jmx/private/meetings/20110610-Conference-Call/Spatial-Temporal-Components.pdf

.. _EVO: http://evo.caltech.edu/evoNext/koala.jnlp?meeting=MIM9Ms2D2iDIDl999aDa9I
