# Higher Genus Curves Database

## Statistics

`hgcwa_unique_groups`: Counts for the per genus list of groups

Column            | Type     | Notes
------------------|----------|------
group             | integer[]| GAP ID encoded as a pair of integers `[N,i]`, where `N` is the order of the group and `i` distinguishes groups of the same order (as determined in GAP or the gps_groups table)
genus             | smallint | genus
g0_is_gt0         | boolean  | whether the group is for quotient genus 0 or quotient genus >= 1
gen_vectors       | integer  | number of distinct generating vectors, up to simultaneous conjugation, for this genus and group
topological       | integer  | number of distinct generating vectors, up to topological equivalence, for this genus and group (if g0_is_gt0 is false)
braids            | integer  | number of distinct generating vectors, up to braid equivalence, for this genus and group (if g0_is_gt0 is false)
g0_gt0_list       | integer[]| list of g0 values this group appears for, if greater than 0
 


## Completeness Records

`hgcwa_complete`: for each genus, list if contains data for quotient genus >0  and whether braid and topological have been computed for that genus

Column            | Type     | Notes
------------------|----------|------
genus             | smallint | genus
g0_gt0_compute    | boolean  | whether quotient genus >0 data has been computed for this genus
top_braid_compute | boolean  | whether topological and braid equivalences have been computed for this genus and g0=0
top_braid_g0_gt0  | boolean  | False for now (whether topological and braid equivalences have been computed for g0>0

