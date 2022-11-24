# organizing_sequences

Once you receive the sequences, drag and drop the whole file into respective folder in geneious. 

Then,

1.Put all bad sequences in a seperate folder
2.Select the good sequences and go Align/Assemble-> De novo assemble
3.Check all the resulting assembly files, check chromatograms and adjust bases when needed
4.for all assembly files, select all of them -> file -> export -> consensus -> ok -> keep sequences seperate -> fasta -> "select save location" -> save

5. Align the fasta sequences using mafft with following command

```bash
mafft --adjustdirectionaccurately temp.fa > temp_aligned.fa
```
or you can simply use the following code changing mydirectory or myfolder 
it will create an aligned file for each file inside my folder with "_aligned" added

```bash
mydirectory="paste/your/directory/here"
myfolder="your_folder_name_here"

for i in ls $mydirectory"/"$myfolder/* ; do echo mafft --adjustdirectionaccurately $i > $i"_aligned.fa" ; done
```
(or set myfolder="/*" to do the same for all the folders inside mydirectory)

6. Create a ne mesquite file
  file -> new -> "select the file path" -> ok
   no of taxa =0
   tick make character matrix ->ok
   Dna data -> ok
   

7. then drag and drop aligned file in mesquite

You can doo the same with single reads, but select 
file -> export -> documents
