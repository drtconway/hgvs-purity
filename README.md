# hgvs-purity
A collection of HGVS nomenclature expressions for testing.

## Background
Clear and unambiguous nomenclature for capturing genetic changes is crucial for research, clinical, and other
applications.  The Human Genome Variation Society (HGVS) has published a set of recommendations for nomenclature which has been widely
adopted at [HGVS](https://varnomen.hgvs.org/).  It is not a formal specification in the sense of, say, HTTP (i.e.
[RFC-7231](https://tools.ietf.org/html/rfc7231)), or [HL7](http://www.hl7.org/).  It does not give a precisely defined
grammar, or semantics, though there are peer reviewed publications such as [den Nunnen et al](https://onlinelibrary.wiley.com/doi/full/10.1002/humu.22981),
which do contain a fairly complete description of the intended form and semantics of the nomenclature.  Unlike standardised notation
such as HTTP (for web traffic) or HL7 (for electronic health records), many uses of HGVS nomenclature are for direct human reading, and
may be written (or transcribed) by humans; moreover, as the nomenclature has evolved many different variations (in some cases
abuses!) have been appeared in databases, papers, and supplementary materials.

In this context, it is natural to use *recommendations* rather than *specifications*, and certainly, it is highly desirable for tools
manipulating HGVS nomenclature to be forgiving, where possible, in the forms of notation they accept. However, it is also desirable
to have a clear and unambiguous formal specification for what constitutes correct notation and what precise semantics that notation
should denote. This is complicated, because a given genetic variation may have more than one equivalent, or nearly equivalent description
under the nomenclature, with subtle differences in semantics. The HGVS nomenclature takes great care to deal with these, and has a
serise of rules for normalising expressions into a canonical form.

Much of the published description of the recommendations is helpfully illustrated by example. What we aim to do here, is compile a
collection of examples, including some from the recommendations, which can be used as test cases by authors in the bioinformatics
community to test parsing, transformation and normalisation of variants. We hope to make it a helpful resource for the community.

## Formats
The examples are given as fragments of JSON, providing genomic (g.), non-coding (n.), coding (c.), and protein (p.) notations
as appropriate, with canonical and non-canonical forms. For the non-canonical forms, a string or a list of strings may be present
if the example is presenting multiple representations that should all canonicalise to the same notation.

It is intended that developers will be able to use the individual syntactic forms to test the scope of parsers and interpretation.
For testing normalisation, all the non-canonical forms should map to the same canonical form.

### Examples

```
{
  "canonical": {
    "coding": "NM_000081.3:c.1884_1886inv",
    "non-coding": "NM_000081.3:n.2066_2068inv",
    "protein": "NP_000072.2:p.(Ile628_Ser629delinsMetIle)"
  }
  "non-canonical": {
    "coding": ["NM_000081.3:c.1883_1887delinsTGATA", "NM_000081.3:c.1883_1887inv"],
    "non-coding": ["NM_000081.3:n.2065_2069delinsTGATA", "NM_000081.3:n.2065_2069inv"]
  }
}
```
