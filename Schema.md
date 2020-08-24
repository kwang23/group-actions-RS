# Higher Genus Curves Database

## Statistics

`gps_groups`: Abstract groups up to isomorphism

Column            | Type     | Notes
------------------|----------|------
group             | integer[]| GAP ID encoded as a pair of integers `[N,i]`, where `N` is the order of the group and `i` distinguishes groups of the same order (as determined in GAP or the gps_groups table)
genus             | smallint | genus
g0_is_gt0         | boolean  | whether the group is for quotient genus 0 or quotient genus >= 1
gen_vectors       | integer  | number of distinct generating vectors, up to simultaneous conjugation, for this genus and group
topological       | integer  | number of distinct generating vectors, up to topological equivalence, for this genus and group (if g0_is_gt0 is false)
braids            | integer  | number of distinct generating vectors, up to braid equivalence, for this genus and group (if g0_is_gt0 is false)
g0_gt0_list       | integer[]| list of g0 values this group appears for, if greater than 0
 

