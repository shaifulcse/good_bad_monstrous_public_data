# good_bad_monstrous_public_data

### Description of the dataset.

There are 49 files for the 49 projects. The first line (header) shows the metrics' names (columns are separated by tab). For each metric measurement, there can be multiple values because we captured the complete evolution history of each method. 

McCabe values 5,6,7 means at the introduction (when the method was first pushed), the McCabe was 5. Then after a change, it became 6, and then 7 (latest).   
But for change values (such as ChangeDates), the first value is always 0. It means the method was introduced that day. The first value is 0 for other change indicators as well, because the method was introduced, not modified.  

ChangeAtMethodAge --- how old was the method when the change happened?

TangledWMoveandFileRename ---how many methods were modified in that commit, without method move and file rename? We have used this information, because if a method is moved in a bug fix commit, but without any content change, then that method should not be responsible for bugs.  

Buggycommiit --- 1 means, it was a bug fix commit according to our accurate keyword-based approach. If it is 1, and the number of TangledWMoveandFileRename is also one, this method version is definitely buggy. This approach was used for the high-precision dataset. 

RiskyCommit ---A method is buggy if the value is 1. This dataset was used for the high-recall dataset. 
