# running-codeml
Notes and scripts on how to run codeml for dn/ds analyses

### Generate the codeml control files in batch AND generate codeml commands that call each control file
```
sh batch_make_control_files_and_print_array_commands.sh
```

### Generate codeml commands referencing each control file

### Collect log likelihood values from batch of completed runs
```
# Example for branch+site model run where null model (H0) and branch-site model (H1) were both run on a set of orthologs
sh parse_codeml_outputs_lnL.sh outputs/OG*/H0/ > branched_sites_H0_combined_lnL.tsv
sh parse_codeml_outputs_lnL.sh outputs/OG*/H1/ > branched_sites_H1_combined_lnL.tsv
```
