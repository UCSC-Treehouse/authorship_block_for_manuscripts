# authorship_block_for_manuscripts
This code generates the authorship block typical for scientific manuscripts, listing all authors with numeric affiliation codes. It puts the affiliations in order of appearance by author order, appends a default university, numbers the affiliations, and creates a text block of affiliations. Next, the numeric codes for the affiliations are appended to each author's name, along with indications of shared first authorship, and outputs the author text. 

# How to use
create an input file using "author_input_data.tsv" as a template. It must include these columns:

* order
* shared author position	
* Author	
* Affiliation

When authors have multiple affiliations, they should all be listed in the "Affiliation" column separated by semicolons 

Because many authors are from the same institution, you can have default suffix to avoid repeating the university and city in affiliations. In that case, if "USA" is not in the affiliation, the default suffix is added. This logic is insufficient for international collaborations.

# Example input
(truncated; see "author_input_data.tsv" above for full input)

order | shared author position | Author | Affiliation
--- | --- | --- | --- 
1 | co-first | Holly C. Beale | Department of Molecular, Cell and Developmental Biology; Genomics Institute
2 | co-first | Katrina Learned | Genomics Institute
3 | co-first | Ellen T. Kephart | Genomics Institute
4 | NA | A. Geoffrey Lyle | Department of Molecular, Cell and Developmental Biology; Genomics Institute
5 | NA | Anouk van den Bout | Department of Molecular, Cell and Developmental Biology; Genomics Institute



# Example output
## Affilation block
```
1. Department of Molecular, Cell and Developmental Biology, University of California Santa Cruz, Santa Cruz, California, USA 
2. Genomics Institute, University of California Santa Cruz, Santa Cruz, California, USA 
3. Division of Pediatric Oncology, University of California San Francisco, San Francisco, California, USA
4. Division of Radiation Oncology, University of California San Francisco, San Francisco, California, USA
5. Department of Biomolecular Engineering, University of California Santa Cruz, Santa Cruz, California, USA
6. Howard Hughes Medical Institute, University of California Santa Cruz, Santa Cruz, California, USA
```

## Author names
```
Holly C. Beale (1,2,*), Katrina Learned (2,*), Ellen T. Kephart (2,*), A. Geoffrey Lyle (1,2), Anouk van den Bout (1,2), Molly McCabe (1,2), Kathryn Echandia-Monroe (1,2), Mansi J Khare (1,2), Elise Y. Huang (1,2), Sheha Jariwala (1,2), Reyna Antilla (1,2), Allison Cheney (1,2), Alex G. Lee (3), Leanne C. Sayles (3), Stanley G. Leung (4), Yvonne A. Vasquez (1,2), Lauren Sanders (1,2), David Haussler (2,5,6), Sofie R. Salama (2,5,6), E. Alejandro Sweet-Cordero (3), Olena M. Vaske (1,2)
```

# Improvements I'd like to see 
- Determining whether an affiliation is incomplete by looking for "USA" in an affiliation is inadequate for non-US authors. 
- Fails if there are no "co-first" authors
- Add support for "co-senior" authors

# Troubleshooting
If you encounter errors, review the session info reported at the end of "generate-author-list-2025.html" to see if your library versions differ from what I use. 

