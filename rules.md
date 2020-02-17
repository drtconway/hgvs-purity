# HGVS Nomenclature Rules

The purpose of the HGVS Nomenclature is to provide a clear and unambiguous way of describing
genetic differences. There are many reasons this is more difficult than it may seem to a
casual observer. The princple reasons that it is difficult are the following:

1. The nomenclature is a description of the difference between two strings,
   which is an under-specified problem in the sense that there can be multiple
   descriptions (or edits) that transform the first string into the second.
   For example, the transformation of `CATTG` to `CATTTG` could be described
   as the insertion of a `T` in 3 possible positions: after the `A`, between the two `T`s,
   or between the second `T` and the `G`.
2. The vocabulary of genetic changes contains more than a minimal set of transformations.
   Describing a change as a `dup` (tandem duplication) rather than an `ins`
   (an arbitrary insertion) is:
    1. more consise (we may omit the sequence from a `dup`, whereas the sequence is required for an `ins`);
    2. more descriptive, since it makes explicit that the inserted sequence is the same as the adjacent sequence in the reference;
    3. more mechanistic, since the presence of identical inserted sequence is indicative of a particular type of mutational event.
   However, this richness exacerbates the problem that a given difference between two
   genetic sequences may now be described in even more ways.
3. The nomenclature allows us to describe genetic changes in multiple domains, and mapping the description
   between domains introduces a range of problems. At a naive level, we should be able to take a genomic DNA
   variant, and express it as a change to a particular gene transcript, and in turn as a change to the protein
   encoded by that transcript. Likewise, we should be able to take either of the other two descriptions and
   express them as changes to the other types of molecule. However, a variety of complications arise since
   the particular way a change is described in one domain does not necessarily fully describe the change in another domain.
   Moreover, since splicing means there is not a simple 1-1 correspondence between genomic and transcript positions,
   it is possible to have genomic changes that may or may not lead do a transcript change depending on which of the
   possible genomic descriptions is used. Likewise, it is possible to have a transcript change which spans a splice
   junction, which can therefore not be fully specified as a genomic change. It clearly matters which description
   is used, and from what actual data it is derived.

To deal with these situations, the HGVS Nomenclature provides a set of rules which govern which descriptions should
be preferred, and which transformations should be allowed, and which should be forbidden. These rules fall into three
categories:
1. Syntactic - such as preferring the use of 3-letter names of amino acids, using LRG accessions, and so on;
2. Positions - such as preferring the description among alternatives that is closest to the 3' end of the reference;
3. Prioritisation - such as preferring to describe a variant as a duplication rather than an insertion, if possible.

