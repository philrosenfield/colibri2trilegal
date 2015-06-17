colibri2trilegal
===============================================
Convert COLIBRI tracks for use in TRILEGAL, make diagnostic TP-AGB plots.

Install
---------------
<pre><code> sudo pip install colibri2trilegal
</pre></code>

Two ways to run:

* Create a template input file: colibri2trilegal -p inputfile
* Convert COLIBRI tracks: colibri2trilegal inputfile

A typical usage would be to create the inputfile using the -p flag, edit it by hand in your favorite editor, and then run colibri2trilgal with the edited inputfile.


The inputfile format
---------------------
<pre><code>

   \# COLIBRI directory structure is [agbtrack_dir]/[agb_mix]/[set_name]
   agbtrack_dir    /home/rosenfield/research/AGBTracks
   agb_mix         CAF09
   set_name        S_NOV13
   
   \# Parameters for TRILEGAL INPUT:
   
   \# Where input files will go for TRILEGAL
   trilegal_dir    cmd_inputfiles/
   
   \# Non-TP-AGB tracks to use
   file_isotrack             isotrack/parsec/CAF09_S12D_NS_1TP.dat
   
   \# mass_loss parameter (for RGB stars) so far only "Reimers: [float]"
   mass_loss       Reimers: 0.2
   
   \# TRILEGAL formatted TP-AGB tracks will go here:
   \# structure: [isotrack_dir]/[agb_mix]/[set_name]
   isotrack_dir    isotrack_agb/
   
   \# File to link TRILEGAL formatted TP-AGB tracks to cmd_input:
   tracce_dir      isotrack_agb/
   
   \### Diag plots, extra files:
   
   \# make initial and final mass relation (and also lifetimes c and m)?
   \# (Need more than one metallicity)
   make_imfr       True
   
   \# Diagnostic plots base, this will have directory structure:
   \# diagnostic_dir/[agb_mix]/[metallicity]/[set]/
   diagnostic_dir0            /home/rosenfield/research/diagnostics/
   
   \# If True, will make HRD or age vs C/O, log L, log Te
   diag_plots  True
   
   \### Misc Options:
   
   \# overwrite TRILEGAL formatted TP-AGB tracks and the output diag plots?
   over_write   True
   
   \# only do these metallicities (if commented out, do all metallicities)
   \#metals_subset       0.001, 0.004, 0.0005, 0.006, 0.008, 0.01, 0.017
</pre></code>
