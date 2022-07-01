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
sh parse_codeml_outputs_lnL.sh outputs/OG*/H0 > branched_sites_H0_combined_lnL.tsv
sh parse_codeml_outputs_lnL.sh outputs/OG*/H1 > branched_sites_H1_combined_lnL.tsv
```

### Make histograms and write lists of significant orthogroups
```
# On fattytubs
dnds_hists.R 
```

### Read the significant orthogroup lists and collect significant orthogroup fastas
```
cp /nfs4/BPP/Uehling_Lab/amsesk/jessie_figure_request/dnds/orthofinder/Single_Copy_Orthologue_Sequences/${p}.fa branch_sig_orthogroups/0.05/.
done < <(cat branch_modles_sig_orthogroups.tsv | cut -f1 | grep -v "^$")
cp /nfs4/BPP/Uehling_Lab/amsesk/jessie_figure_request/dnds/orthofinder/Single_Copy_Orthologue_Sequences/${p}.fa branch_sig_orthogroups/0.01/.
done < <(cat branch_modles_sig_orthogroups.tsv | cut -f2 | grep -v "^$")
cp /nfs4/BPP/Uehling_Lab/amsesk/jessie_figure_request/dnds/orthofinder/Single_Copy_Orthologue_Sequences/${p}.fa branch_sig_orthogroups/0.001/.
done < <(cat branch_modles_sig_orthogroups.tsv | cut -f3 | grep -v "^$")
```
