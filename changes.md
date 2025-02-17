# Changes

## 14.06.23

### Bugs:
B1. incorrect clock_unit property (4000, should be 480)
B2. for Chopin_op38: last performed midi note missing in all match files except for last one (in last performance, last four notes are ommitted)
B3. for Chopin_op10_no3: voice-overlap score notes are missing in match files (those notes should get a new id, and should be aligned as deletions with score attribution 'voice_overlap')
B4. Missing MIDI performance notes in match file: 
    - for Chopin_op38: each MIDI performance has notes (except for the last one addressed in B2) that are missing in alignment. Similarly most match alignments have score notes marked as deletions
    - for Mozart_K331_1st-mov perf15 has non-aligned midi note n488
    - for Schubert_D783_no15 perf2 has non-aligned midi note n334, perf6 has non-aligned midi note n328
    

### Changes made:
C1. (fix for B2) Recreated match files for Chopin_op38 adding missing last performed note and 480 clock clock_unit 
C2. (fix for B1) Recreated match files for all pieces with 480 clock_unit


### Notes on B3 and B4:
B3: musicxml has no 'voice_overlap' tag or attribute, any solution (change in save_match/matchfile_from_alignment) would involve an additional function param (i.e., ids/indices of score notes where voice_overlap attribute should be added)
B4: see updated_match_alignments/_missing_notes.txt for list of missing notes for each performance/piece (created after fix for B2, voice_overlap_notes for Chopin_op10_no3 not included)

ph, 14.06.23

## 07.03.24

* Update starting time of MIDI and and Matchfiles to start with the audio files.
* Add script to setup the audio files.