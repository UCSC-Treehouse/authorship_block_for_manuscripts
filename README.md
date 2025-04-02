# authorship_block_for_manuscripts
This code generates the authorship block typical for scientific manuscripts, listing all authors with numeric affiliation codes

# How to use
create an input file using "author_input_data.tsv" as a template. It must include these columns:

* order
* shared author position	
* Author	
* Affiliation

When authors have multiple affiliations, they should all be listed in the "Affiliation" column separated by semicolons 

Because many authors are from the same institution, you can have default suffix to avoid repeating the university and city in affiliations. In that case, if "USA" is not in the affiliation, the default suffix is added. This logic is insufficient for international collaborations.


# Improvements I'd like to see 
- Determining whether an affiliation is incomplete by looking for "USA" in an affiliation is inadequate for non-US authors. 
- Fails if there are no "co-first" authors
- Add support for "co-senior" authors

